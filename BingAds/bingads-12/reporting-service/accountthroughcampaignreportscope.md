---
title: AccountThroughCampaignReportScope Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the set of accounts and campaigns to include in the report.
---
# AccountThroughCampaignReportScope Data Object - Reporting
Defines the set of accounts and campaigns to include in the report.

The report scope includes a union of the included [AccountIds](#accountids) and [Campaigns](#campaigns) elements.

## Syntax
```xml
<xs:complexType name="AccountThroughCampaignReportScope" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountIds" nillable="true" type="q2:ArrayOflong" xmlns:q2="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="Campaigns" nillable="true" type="tns:ArrayOfCampaignReportScope" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|An array of account identifiers that identifies the account data to include in the report.<br/><br/>You can include a maximum of 1,000 account identifiers.|**long** array|
|<a name="campaigns"></a>Campaigns|An array of *CampaignReportScope* objects that identifies the campaign data to include in the report.<br/><br/>You can include a maximum of 300 campaigns.|[CampaignReportScope](campaignreportscope.md) array|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[BudgetSummaryReportRequest](budgetsummaryreportrequest.md)  
[CampaignPerformanceReportRequest](campaignperformancereportrequest.md)  
