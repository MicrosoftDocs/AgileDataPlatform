# Data Classification for Environments

**produced by Dave Lusty**

## Introduction

This document aims to clear up some misconceptions around data classification and staging environments. The terms "dev", "test" and "production" are ubiquitous yet often misunderstood for legacy reasons. As we move into a more agile and cloud centric world it becomes more important to fully understand what data is where and why.

## Production Data

The term production data is often used to refer to the actual business data. As such, the term production can be misleading since it implies that data is in the production environment. There are various considerations which can make this clear, with new classifications laid out below.
<table>
<tr>
<td width="25%">&nbsp;</td>
<td width="50%"><img src="images/PrimarySafeLiveExperimental.png" /></td>
<td width="25%">&nbsp;</td>
</tr>
</table>

### Is this the primary copy of the data?

In all computing, there are systems of record. These are the place where data is created and edited. Sometimes data is copied to multiple systems and worked on in both locations. In such instances both can be considered systems of record, and therefore the data within them is what I will refer to as **"primary data"**. This means that the data is the source data and is unadulterated.

### Is the data on a line of business system?

This question is important. Primary data may be copied to other production systems. The data may still be unadulterated primary data, or it may be modified in some way. Because it is running on a production system (for example a data warehouse, or data lake) it must have suitable governance to ensure it is not accidentally corrupted in any way. I will refer to this data as **"live data"** since it may no longer be primary if the data has been modified, but is still sufficiently important for tight controls. This classification is entirely centred around whether changes in data will be problematic for the business and so is generally in scenarios where the data will be used for a business function.

Primary data may also be copied to systems which are not business affecting, in order to allow it to be used in a less safe way. These systems might be production quality or not, but the data will not be used for business functions directly. This does not alter the data classification in and of itself, and so any data governance controls in place in production such as security access or privacy controls must still be used. The difference here is that if the data is in any way corrupted the business will not be interrupted in any way. This allows users to try things out on the data without consequences, and data can be copied from a primary source again to refresh the data. I will refer to this data as **"experimental data"**. Note that this is distinct from "test data" which is discussed later in the document. Experimental data can be used on systems in a production environment, for instance for machine learning workloads where training models is a business function the training and experimentation systems are governed as production systems but the experimental data can have relaxed controls. 

### Has the data been modified for privacy or compliance reasons?

Primary data may be copied and modified to remove specific information, for example personally identifiable information (PII) or credit card information (for regulatory reasons). The destination of this copy does not affect the classification of the data, it may be a development location or a production location. The act of cleansing the data is designed to make the data safer to user or share. In all instances, the data classification will change from primary data with very strict controls around use, security, movement and processing to what I will call **"safe data"** which might have less stringent controls for the purposes of data manipulation. If the safe data remains in a live environment, then the production governance will still apply to ensure that the safe data does not become corrupted or unusable, but this is distinct from the data security and compliance controls which may be relaxed.

## Test Data

<table>
<tr>
<td width="25%">&nbsp;</td>
<td width="50%"><img src="images/TestData.png" /></td>
<td width="25%">&nbsp;</td>
</tr>
</table>

### Structured Testing

The pass/fail nature of structured testing means that you must have an assertion and a known answer. This is not possible to do with fresh data from live systems in any controlled or repeatable manner. For this reason **"Test Data"** must be user generated based on those assertions and answers. If you are testing an aggregation then you must generate known data, manually compute the aggregation and then set that as the answer to the test. This way the test is repeatable and has a different path than the thing you are testing.

### Accuracy Testing

Machine learning tests are very different to structured testing and instead often incorporate some manual statistical analysis. In this instance it is likely that your "test data" is just part of your data set and so a different data set may not be required, or may just be a partial copy to a new location.

<table>
<tr>
<td width="15%">&nbsp;</td>
<td width="70%"><img src="images/flowchart.png" /></td>
<td width="15%">&nbsp;</td>
</tr>
</table>

In a real scenario this might look like the below
<table>
<tr>
<td width="15%">&nbsp;</td>
<td width="70%"><img src="images/classificationFlow.png" /></td>
<td width="15%">&nbsp;</td>
</tr>
</table>

## Data Classifications

### Primary Data

<table>
<tr>
<td>Operational Governance</td>
<td bgcolor="#ff3333"><font color="#000000">yes</font></td>
</tr>
<tr>
<td>Regulatory Governance</td>
<td bgcolor="#ff3333"><font color="#000000">yes</font></td>
</tr>
</table>

Primary data will have full governance applied. This data sits within a production environment and so must be protected against loss and corruption through access controls, backups and other normal operational procedures. 
It might also need regulatory governance to be applied if there is sensitive data included. This might require stricter access controls, movement controls, encryption and other methods used to protect the data from being accessed outside of known and controlled use-cases.

### Live Data

<table>
<tr>
<td>Operational Governance</td>
<td bgcolor="#ff3333"><font color="#000000">yes</font></td>
</tr>
<tr>
<td>Regulatory Governance</td>
<td bgcolor="#33ccff"><font color="#000000">N/A</font></td>
</tr>
</table>

Live data might be a copy of primary data or primary data itself. This data sits within a production environment and so must be protected against loss and corruption through access controls, backups and other normal operational procedures. The live designation does not affect sensitivity levels and so regulatory governance may or may not need to be applied depending on the data.

### Experimental Data

<table>
<tr>
<td>Operational Governance</td>
<td bgcolor="#33ff33"><font color="#000000">No</font></td>
</tr>
<tr>
<td>Regulatory Governance</td>
<td bgcolor="#33ccff"><font color="#000000">N/A</font></td>
</tr>
</table>

Experimental data might be a copy of primary data but will not be primary data itself. This data might not sit in a line of business system and so the data does not need to be protected against loss and corruption through access controls, backups and other normal operational procedures. The system which consumes, processes or hosts it might be classified as production and itself be subject to that operational governance. The live designation does not affect sensitivity levels and so regulatory governance may or may not need to be applied depending on the data.

### Safe Data

<table>
<tr>
<td>Operational Governance</td>
<td bgcolor="#33ccff"><font color="#000000">N/A</font></td>
</tr>
<tr>
<td>Regulatory Governance</td>
<td bgcolor="#ff3333"><font color="#000000">No</font></td>
</tr>
</table>

Safe data has been modified in some way to reduce the specific data governance controls applied to that data in order to make it more accessible, shareable, or less cumbersome to consume. This does not affect operational governance, but is designed to reduce regulatory governance. 

### Test Data

<table>
<tr>
<td>Operational Governance</td>
<td bgcolor="#33ccff"><font color="#000000">N/A</font></td>
</tr>
<tr>
<td>Regulatory Governance</td>
<td bgcolor="#33ccff"><font color="#000000">N/A</font></td>
</tr>
</table>

Since test data is generated for a specific purpose the governance will depend entirely on the systems consuming it. As a general rule, test data is a part of a production pipeline used for testing systems, and so will be protected with operational governance. While the data will certainly not be subject to regulatory governance, it might appear similar to sensitive data and so some thought should still be given to the consequences of a data breach, even if those consequences are only reputational. In some instances, sensitive data such as test credit card numbers may be included in test data, in which case strong data governance will be required.