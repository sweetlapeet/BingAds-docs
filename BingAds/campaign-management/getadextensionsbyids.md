---
title: GetAdExtensionsByIds Service Operation
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetAdExtensionsByIds Service Operation
Gets the specified ad extensions from the account?s ad extension library.

## <a name="request"></a>Request Elements
The *GetAdExtensionsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the ad extensions.|**long**|
|<a name="adextensionids"></a>AdExtensionIds|A list of ad extension identifiers. You can specify a maximum of 100 identifiers.|**long**|
|<a name="adextensiontype"></a>AdExtensionType|The types of ad extensions that the list of identifiers contains.|[AdExtensionsTypeFilter](adextensionstypefilter.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdExtensionsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensions"></a>AdExtensions|A list of [AdExtension](../campaign-management/adextension.md) objects. The list corresponds directly to the list of identifiers in the request. If an ad extension ID in the request is not valid or the extension is not of the type specified, the corresponding item in this list is null.|[AdExtension](adextension.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetAdExtensionsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdExtensionsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <AdExtensionIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdExtensionIds>
      <AdExtensionType>ValueHere</AdExtensionType>
    </GetAdExtensionsByIdsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAdExtensionsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdExtensions d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdExtension d4p1:type="-- derived type specified here with the appropriate prefix --">
          <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
          <ForwardCompatibilityMap xmlns:e594="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e594:KeyValuePairOfstringstring>
              <e594:key d4p1:nil="false">ValueHere</e594:key>
              <e594:value d4p1:nil="false">ValueHere</e594:value>
            </e594:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Scheduling d4p1:nil="false">
            <DayTimeRanges d4p1:nil="false">
              <DayTime>
                <Day>ValueHere</Day>
                <EndHour>ValueHere</EndHour>
                <EndMinute>ValueHere</EndMinute>
                <StartHour>ValueHere</StartHour>
                <StartMinute>ValueHere</StartMinute>
              </DayTime>
            </DayTimeRanges>
            <EndDate d4p1:nil="false">
              <Day>ValueHere</Day>
              <Month>ValueHere</Month>
              <Year>ValueHere</Year>
            </EndDate>
            <StartDate d4p1:nil="false">
              <Day>ValueHere</Day>
              <Month>ValueHere</Month>
              <Year>ValueHere</Year>
            </StartDate>
            <UseSearcherTimeZone d4p1:nil="false">ValueHere</UseSearcherTimeZone>
          </Scheduling>
          <Status d4p1:nil="false">ValueHere</Status>
          <Type d4p1:nil="false">ValueHere</Type>
          <Version d4p1:nil="false">ValueHere</Version>
          <!--This field is applicable if the derived type attribute is set to SiteLinksAdExtension-->
          <SiteLinks d4p1:nil="false">
            <SiteLink>
              <Description1 d4p1:nil="false">ValueHere</Description1>
              <Description2 d4p1:nil="false">ValueHere</Description2>
              <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
              <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
              <DisplayText d4p1:nil="false">ValueHere</DisplayText>
              <FinalAppUrls xmlns:e595="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                <e595:AppUrl>
                  <e595:OsType d4p1:nil="false">ValueHere</e595:OsType>
                  <e595:Url d4p1:nil="false">ValueHere</e595:Url>
                </e595:AppUrl>
              </FinalAppUrls>
              <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalMobileUrls>
              <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalUrls>
              <Scheduling d4p1:nil="false">
                <DayTimeRanges d4p1:nil="false">
                  <DayTime>
                    <Day>ValueHere</Day>
                    <EndHour>ValueHere</EndHour>
                    <EndMinute>ValueHere</EndMinute>
                    <StartHour>ValueHere</StartHour>
                    <StartMinute>ValueHere</StartMinute>
                  </DayTime>
                </DayTimeRanges>
                <EndDate d4p1:nil="false">
                  <Day>ValueHere</Day>
                  <Month>ValueHere</Month>
                  <Year>ValueHere</Year>
                </EndDate>
                <StartDate d4p1:nil="false">
                  <Day>ValueHere</Day>
                  <Month>ValueHere</Month>
                  <Year>ValueHere</Year>
                </StartDate>
                <UseSearcherTimeZone d4p1:nil="false">ValueHere</UseSearcherTimeZone>
              </Scheduling>
              <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
              <UrlCustomParameters xmlns:e596="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
                <e596:Parameters d4p1:nil="false">
                  <e596:CustomParameter>
                    <e596:Key d4p1:nil="false">ValueHere</e596:Key>
                    <e596:Value d4p1:nil="false">ValueHere</e596:Value>
                  </e596:CustomParameter>
                </e596:Parameters>
              </UrlCustomParameters>
            </SiteLink>
          </SiteLinks>
          <!--These fields are applicable if the derived type attribute is set to LocationAdExtension-->
          <Address d4p1:nil="false">
            <CityName d4p1:nil="false">ValueHere</CityName>
            <CountryCode d4p1:nil="false">ValueHere</CountryCode>
            <PostalCode d4p1:nil="false">ValueHere</PostalCode>
            <ProvinceCode d4p1:nil="false">ValueHere</ProvinceCode>
            <ProvinceName d4p1:nil="false">ValueHere</ProvinceName>
            <StreetAddress d4p1:nil="false">ValueHere</StreetAddress>
            <StreetAddress2 d4p1:nil="false">ValueHere</StreetAddress2>
          </Address>
          <CompanyName d4p1:nil="false">ValueHere</CompanyName>
          <GeoCodeStatus d4p1:nil="false">ValueHere</GeoCodeStatus>
          <GeoPoint d4p1:nil="false">
            <LatitudeInMicroDegrees>ValueHere</LatitudeInMicroDegrees>
            <LongitudeInMicroDegrees>ValueHere</LongitudeInMicroDegrees>
          </GeoPoint>
          <IconMediaId d4p1:nil="false">ValueHere</IconMediaId>
          <ImageMediaId d4p1:nil="false">ValueHere</ImageMediaId>
          <PhoneNumber d4p1:nil="false">ValueHere</PhoneNumber>
          <!--These fields are applicable if the derived type attribute is set to CallAdExtension-->
          <CountryCode d4p1:nil="false">ValueHere</CountryCode>
          <IsCallOnly d4p1:nil="false">ValueHere</IsCallOnly>
          <IsCallTrackingEnabled d4p1:nil="false">ValueHere</IsCallTrackingEnabled>
          <PhoneNumber d4p1:nil="false">ValueHere</PhoneNumber>
          <RequireTollFreeTrackingNumber d4p1:nil="false">ValueHere</RequireTollFreeTrackingNumber>
          <!--These fields are applicable if the derived type attribute is set to ImageAdExtension-->
          <AlternativeText d4p1:nil="false">ValueHere</AlternativeText>
          <Description d4p1:nil="false">ValueHere</Description>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <FinalAppUrls xmlns:e597="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e597:AppUrl>
              <e597:OsType d4p1:nil="false">ValueHere</e597:OsType>
              <e597:Url d4p1:nil="false">ValueHere</e597:Url>
            </e597:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <ImageMediaIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </ImageMediaIds>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e598="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e598:Parameters d4p1:nil="false">
              <e598:CustomParameter>
                <e598:Key d4p1:nil="false">ValueHere</e598:Key>
                <e598:Value d4p1:nil="false">ValueHere</e598:Value>
              </e598:CustomParameter>
            </e598:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to AppAdExtension-->
          <AppPlatform d4p1:nil="false">ValueHere</AppPlatform>
          <AppStoreId d4p1:nil="false">ValueHere</AppStoreId>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <DisplayText d4p1:nil="false">ValueHere</DisplayText>
          <FinalAppUrls xmlns:e599="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e599:AppUrl>
              <e599:OsType d4p1:nil="false">ValueHere</e599:OsType>
              <e599:Url d4p1:nil="false">ValueHere</e599:Url>
            </e599:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e600="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e600:Parameters d4p1:nil="false">
              <e600:CustomParameter>
                <e600:Key d4p1:nil="false">ValueHere</e600:Key>
                <e600:Value d4p1:nil="false">ValueHere</e600:Value>
              </e600:CustomParameter>
            </e600:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to ReviewAdExtension-->
          <IsExact>ValueHere</IsExact>
          <Source d4p1:nil="false">ValueHere</Source>
          <Text d4p1:nil="false">ValueHere</Text>
          <Url d4p1:nil="false">ValueHere</Url>
          <!--This field is applicable if the derived type attribute is set to CalloutAdExtension-->
          <Text d4p1:nil="false">ValueHere</Text>
          <!--These fields are applicable if the derived type attribute is set to Sitelink2AdExtension-->
          <Description1 d4p1:nil="false">ValueHere</Description1>
          <Description2 d4p1:nil="false">ValueHere</Description2>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <DisplayText d4p1:nil="false">ValueHere</DisplayText>
          <FinalAppUrls xmlns:e601="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e601:AppUrl>
              <e601:OsType d4p1:nil="false">ValueHere</e601:OsType>
              <e601:Url d4p1:nil="false">ValueHere</e601:Url>
            </e601:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e602="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e602:Parameters d4p1:nil="false">
              <e602:CustomParameter>
                <e602:Key d4p1:nil="false">ValueHere</e602:Key>
                <e602:Value d4p1:nil="false">ValueHere</e602:Value>
              </e602:CustomParameter>
            </e602:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to StructuredSnippetAdExtension-->
          <Header d4p1:nil="false">ValueHere</Header>
          <Values d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </Values>
          <!--These fields are applicable if the derived type attribute is set to PriceAdExtension-->
          <Language d4p1:nil="false">ValueHere</Language>
          <PriceExtensionType>ValueHere</PriceExtensionType>
          <TableRows d4p1:nil="false">
            <PriceTableRow>
              <CurrencyCode d4p1:nil="false">ValueHere</CurrencyCode>
              <Description d4p1:nil="false">ValueHere</Description>
              <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalMobileUrls>
              <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </FinalUrls>
              <Header d4p1:nil="false">ValueHere</Header>
              <Price>ValueHere</Price>
              <PriceQualifier>ValueHere</PriceQualifier>
              <PriceUnit>ValueHere</PriceUnit>
              <TermsAndConditions d4p1:nil="false">ValueHere</TermsAndConditions>
              <TermsAndConditionsUrl d4p1:nil="false">ValueHere</TermsAndConditionsUrl>
            </PriceTableRow>
          </TableRows>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e603="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e603:Parameters d4p1:nil="false">
              <e603:CustomParameter>
                <e603:Key d4p1:nil="false">ValueHere</e603:Key>
                <e603:Value d4p1:nil="false">ValueHere</e603:Value>
              </e603:CustomParameter>
            </e603:Parameters>
          </UrlCustomParameters>
        </AdExtension>
      </AdExtensions>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e604="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e604:KeyValuePairOfstringstring>
              <e604:key d4p1:nil="false">ValueHere</e604:key>
              <e604:value d4p1:nil="false">ValueHere</e604:value>
            </e604:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to EditorialError-->
          <Appealable d4p1:nil="false">ValueHere</Appealable>
          <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
          <Location d4p1:nil="false">ValueHere</Location>
          <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
          <ReasonCode>ValueHere</ReasonCode>
        </BatchError>
      </PartialErrors>
    </GetAdExtensionsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<GetAdExtensionsByIdsResponse> GetAdExtensionsByIdsAsync(
	long accountId,
	IList<long> adExtensionIds,
	AdExtensionsTypeFilter adExtensionType)
{
	var request = new GetAdExtensionsByIdsRequest
	{
		AccountId = accountId,
		AdExtensionIds = adExtensionIds,
		AdExtensionType = adExtensionType
	};

	return (await CampaignManagement.CallAsync((s, r) => s.GetAdExtensionsByIdsAsync(r), request));
}
```
```java
static GetAdExtensionsByIdsResponse getAdExtensionsByIds(
	long accountId,
	ArrayOflong adExtensionIds,
	AdExtensionsTypeFilter adExtensionType)
{
	GetAdExtensionsByIdsRequest request = new GetAdExtensionsByIdsRequest();

	request.setAccountId(accountId);
	request.setAdExtensionIds(adExtensionIds);
	request.setAdExtensionType(adExtensionType);

	return CampaignManagement.getService().getAdExtensionsByIds(request);
}
```
```php
static function GetAdExtensionsByIds(
	$accountId,
	$adExtensionIds,
	$adExtensionType)

	$getAdExtensionsByIdsRequest = new GetAdExtensionsByIdsRequest();

	$request->AccountId = $accountId;
	$request->AdExtensionIds = $adExtensionIds;
	$request->AdExtensionType = $adExtensionType;

	return $CampaignManagementProxy->GetService()->GetAdExtensionsByIds($request);
}
```
```python
response=campaignmanagement.GetAdExtensionsByIds(
	AccountId=AccountIdHere,
	AdExtensionIds=AdExtensionIdsHere,
	AdExtensionType=AdExtensionTypeHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  
