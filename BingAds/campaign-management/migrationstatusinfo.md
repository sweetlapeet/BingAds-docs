---
title: MigrationStatusInfo Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# MigrationStatusInfo Data Object
Defines an object that contains the migration type and status for an account.

## Syntax
```xml
<xs:complexType name="MigrationStatusInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="MigrationType" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="StartTimeInUtc" nillable="true" type="xs:dateTime" />
    <xs:element name="Status" type="tns:MigrationStatus" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="migrationtype"></a>MigrationType|The migration type.|**string**|
|<a name="starttimeinutc"></a>StartTimeInUtc|The date and time when the migration began. The value is in Coordinated Universal Time (UTC).<br/><br/>**Note:** The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|
|<a name="status"></a>Status|The migration status.|[MigrationStatus](migrationstatus.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AccountMigrationStatusesInfo](accountmigrationstatusesinfo.md)  