# ![LOGO](logo.png) Adyen MarketPay Account Service MSP Connector

## Description

A generated MSP connector for the Adyen MarketPay Account Service API (version 4).

Generated from: https://api.apis.guru/v2/specs/adyen.com/AccountService/4/openapi.json<br/>
Generated at: 2019-05-07T11:15:11+03:00

## API Description

The MarketPay Account API provides endpoints for managing MarketPay account-related entities. These related entities include account holders, accounts, bank accounts, shareholders, and KYC-related documents. The management operations include actions such as creation, retrieval, updating, and deletion of them.

For further information on MarketPay API, visit the [MarketPay documentation](https://docs.adyen.com/developers/marketpay/marketpay-overview).
## Authentication
To connect to the MarketPay API, you must use basic authentication credentials of your web service user. If you don't have one, please contact the [Adyen Support Team](https://support.adyen.com/hc/en-us/requests/new). Then use its credentials to authenticate your request, for example:

```
curl
-U "ws@Company.YourCompany":"YourWsPassword" \
-H "Content-Type: application/json" \
...
```
Note that when going live, you need to generate new web service user credentials to access the [live endpoints](https://docs.adyen.com/developers/api-reference/live-endpoints).

## Versioning
MarketPay API supports versioning of its endpoints through a version suffix in the endpoint URL. This suffix has the following format: "vXX", where XX is the version number.

For example:
```
https://cal-test.adyen.com/cal/services/Account/v4/createAccountHolder
```

## Authorization

This API does not require authorization.

## Actions

### Close an existing account under an account holder.

> This endpoint is used to close an existing account under an account holder. If an account is closed, it may not process transactions or have its funds paid out,and it may not be reopened. Any payments made to a closed account will be directed to the merchant's liable account.

### Close an existing account holder.

> This endpoint is used to close an existing account holder and its accounts. If an account holder is closed, it may not process transactions or pay out funds, and it may not be reopened. Any payments made to a closed account will be directed to the merchant's liable account.

### Create a new account under an existing account holder.

> This endpoint is used to create an account under an existing account holder. An account holder may have multiple accounts.

### Create a new account holder.

> This endpoint is used to create an account holder. Each account holder represents a single sub-merchant, and each sub-merchant must be represented by an account holder. Depending on the legal entity type, different details are required to be provided in the call to this endpoint.

### Delete bank accounts of an existing account holder.

> This endpoint is used to delete existing bank accounts from an account holder. For this, pass the `accountHolderCode` you got on the account holder creation, and one or more `bankAccountUUIDs` specifying bank accounts to delete.

### Delete shareholders of an existing account holder.

> This endpoint is used to delete existing shareholders from an account holder.

### Retrieve the details of an account holder.

> This endpoint is used to retrieve the details of an account holder.

### Retrieve the uploaded documents of an existing account holder.

> This endpoint is used to retrieve documents previously uploaded for use in the KYC Verification of an account holder.<br/>
> <br/>
> For further information regarding KYC Verification, please refer to [Verification checks](https://docs.adyen.com/developers/marketpay/onboarding-and-verification/verification-checks).

### Suspend an existing account holder.

> This endpoint is used to suspend an existing account holder. If an account holder is suspended, it may not process transactions or pay out funds. Any payments made to a suspended account holder will be directed to the merchant's liable account.

### Reinstate a disabled account holder.

> This endpoint is used to reinstate an existing account holder, which has been suspended through the `/suspendAccountHolder` endpoint. An account holder which has been suspended due to KYC verification issues cannot be reinstated through this endpoint.

### Update an existing account under an account holder.

> This endpoint is used to update the description or payout schedule of an existing account.

### Update an existing account holder.

> This endpoint is used to update the `accountHolderDetails` or `processingTier` of an account holder.<br/>
> <br/>
> If updating the `accountHolderDetails`, only the details which have been provided will be updated. Other details will be left as-is with the exception of the following fields:<br/>
> * `accountHolderDetails.address`<br/>
> * `accountHolderDetails.phoneNumber`<br/>
> * `accountHolderDetails.bankAccountDetails.BankAccountDetail`<br/>
> * `accountHolderDetails.businessDetails.shareholders.ShareholderContact`, which requires all fields necessary for validation (i.e. in order to update only the `accountHolderDetails.address.postalCode`, the fields `accountHolderDetails.address.country`, `.city`, `.street`, `.postalCode`, and possibly `.stateOrProvince` must be provided as well, so that the address can be properly validated).<br/>
> <br/>
> Note that this endpoint can also be used to create new bank accounts. For this, provide details of a bank account without providing a `bankAccountUUID`.<br/>
> <br/>
> Similarly, it can also be used to create new shareholders by providing details of a shareholder without providing a `shareholderCode`.<br/>
> > The updating of the `metadata` field will overwite all of the existing account holder metadata. In order to update an existing metadata key-value pair, all otherkey-value pairs should be provided in order to not delete them.

### Update the state of an existing account holder.

> This endpoint is used to disable or enable the processing or payout state of an account holder. It cannot be used to enable an account holder whose processing or payout state has not been disabled through this endpoint.<br/>
> <br/>
> For further information regarding processing and payout states of an account holder, please refer to the [MarketPay documentation](https://docs.adyen.com/developers/marketpay/marketpay-overview).

### Upload a document for an existing account holder.

> This endpoint is used to upload a document for use in the KYC verification of an account holder.<br/>
> <br/>
> For further information regarding KYC Verification, please refer to [Verification checks](https://docs.adyen.com/developers/marketpay/onboarding-and-verification/verification-checks).

## License

flowground :- Telekom iPaaS / adyen-com-account-service-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
