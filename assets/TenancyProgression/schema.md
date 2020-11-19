
| SQL | Schema | Mandatory| Data |
|--|--|--|--|
||\Operation|X|Create|
||\hub\Tenancy\TenancyId|X||
||\hub\Tenancy\StartDate|X||
||\hub\Tenancy\EndDate|||
|Tenancy\RentFrequencyId|\hub\Tenancy\Duration|||
|Tenancy\AgreedWeeklyRent|\hub\Tenancy\Rent|X||
||\hub\Tenancy\Deposit|X||
||\hub\Tenancy\DepositReceivedDate|X||
||\Property\Address|X||
|Tenancy\AssetId\AddressId\PropertyNumber|\Property\Address\PropertyNumber|X||
|Tenancy\AssetId\AddressId\PropertyName|\Property\Address\PropertyName|X||
|Tenancy\AssetId\AddressId\Line1|\Property\Address\Line1|||
|Tenancy\AssetId\AddressId\Lines|\Property\Address\Line2|||
|Tenancy\AssetId\AddressId\Line3|\Property\Address\Line3|||
|Tenancy\AssetId\AddressId\County|\Property\Address\County|||
|Tenancy\AssetId\AddressId\PostCode|\Property\Address\PostCode|X||
||\Property\Address\Country|X||
||\Property\Address\Country\Iso2Char|X||
|Tenancy\AssetId\AddressId\CountryId\DiallingCode|\Property\Address\Country\DialingCode|X||
|Tenancy\AssetId\AddressId\CountryId\CurrencyId\Code|\Property\Address\Country\CurrencyCode|X||
||\People\Person[0]|X||
|**Landlord Contact Details**|\People\Person[0]\PersonType|X|Landlord|
||\People\Person[0]\ExistingLandlordId|||
||\People\Person[0]\Contact|X||
||\People\Person[0]\Salutation|X||
||\People\Person[0]\FirstName|X||
||\People\Person[0]\LastName|X||
||\People\Person[0]\ContactEmail|X||
||\People\Person[0]\ContactMobile|||
||\People\Person[0]\ContactPhone|X||
||\People\Person[0]\Address|X||
||\People\Person[0]\Address\PropertyNumber|X||
||\People\Person[0]\Address\PropertyName|X||
||\People\Person[0]\Address\Line1|||
||\People\Person[0]\Address\Line2|||
||\People\Person[0]\Address\Line3|||
||\People\Person[0]\Address\County|||
||\People\Person[0]\Address\PostCode|X||
||\People\Person[0]\Address\Country|X||
||\People\Person[0]\Address\Country\CountryIso2Char|X||
||\People\Person[0]\Address\Country\CountryDialingCode|X||
||\People\Person[0]\Address\Country\Country"CurrencyCode|X||
|**Lead Tenant Contact Details**|\People\Person[1]|X||
||\People\Person[1]\PersonType|X|LeadTenant|
||\People\Person[1]\ExistingLandlordId|||
||\People\Person[1]\Contact|X||
||\People\Person[1]\Salutation|X||
|TenancyParty.TenancyId = TenancyId, TenancyParty.ContactId\FirstName|\People\Person[1]\FirstName|X||
|TenancyParty.TenancyId = TenancyId, TenancyParty.ContactId\LastName|\People\Person[1]\LastName|X||
|(TenancyParty.ContactId Where RoleId in {'Tenant','PermittedOccupant', 'HeadTenant'} , TenancyParty.ContactId = ContactEmail.ContactId) ContactEmail.Email|\People\Person[1]\ContactEmail|X||
|(TenancyParty.TenancyId = TenancyId, TenancyParty.ContactId = ContactPhone.ContactId, ContactPhone.PhoneTypeId = 'PhoneTypeMobile') ContactPhone.Number|\People\Person[1]\ContactMobile|||
|(TenancyParty.TenancyId = TenancyId, TenancyParty.ContactId = ContactPhone.ContactId, ContactPhone.PhoneTypeId = 'PhoneTypeMobile') ContactPhone.Number|\People\Person[1]\ContactPhone|X||
||\People\Person[1]\Address|X||
||\People\Person[1]\Address\PropertyNumber|X||
||\People\Person[1]\Address\PropertyName|X||
||\People\Person[1]\Address\Line1|||
||\People\Person[1]\Address\Line2|||
||\People\Person[1]\Address\Line3|||
||\People\Person[1]\Address\County|||
||\People\Person[1]\Address\PostCode|X||
||\People\Person[1]\Address\Country|X||
||\People\Person[1]\Address\Country\CountryIso2Char|X||
|(TenancyParty.TenancyId = TenancyId, TenancyParty.ContactId Where in {'Tenant','PermittedOccupant', 'HeadTenant'} , TenancyParty.ContactId = ContactAddress.ContactId) AddressId\CountryId\DiallingCode|\People\Person[1]\Address\Country\CountryDialingCode|X||
|(TenancyParty.TenancyId = TenancyId, TenancyParty.ContactId = ContactAddress.ContactId)\AddressId\CountryId\CurrencyId\Code	|\People\Person[1]\Address\Country\CurrencyCode|X||
||\TDS|X||
|New Db Field|\TDS\MemberId|X||
|New Db Field|\TDS\BranchId|X||
||\TDS\Success|||
|New Db Field|\TDS\Api_Reference|||
|New Db Field|\TDS\Certificate|||
||\TDS\Errors[0]\ErrorCode|||
||\TDS\Errors[0]\Error|||



