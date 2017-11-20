# api-introduction
A basic introduction to the TASS API's.

**Examples**

  * encryptDecrypt.cs - A basic C# Encrypt and Decrypt class example
  * POST.html - A HTML page with a form
  * GET.html - A HTML page with an anchor

**Request URL Construction**

* **Overview**

	The request URL is constructed using several parts.

	```HTML
	{protocol}://{domain}/tassweb/api/?method={method}&appcode={appcode}&company={companycode}&v=2&token={token}
	````

* **Protocol**

	The protocol is defined in the TASS API Setup in tass.web. This can be set to allow HTTP or HTTPS requests. It can also be set to restrict requests to HTTPS only.

* **Domain**

	The domain of the tass.web server you wish to make the request to.

* **Method**

	The API Method you wish to invoke.

* **App Code**

	The App Code as defined in the tass.web TASS API Setup.

* **Company Code**

	The Company Code for which the TASS API App has been configured in tass.web.

* **Token**

	The token is generated by encrypting the parameter string with your Token Key.

	```JAVASCRIPT
	Encrypt( '{"include_label":"true"}'
	, '+TG1ZTqy0hTu5h0KMhCP0A=='
	, 'AES/ECB/PKCS5Padding'
	, 'Base64')
	```

	Expected Token

	```HTML
	96yfUt3jgAIYx0o7i3tjprnBpotNO3Md/yv+eToJ8qo=
	```

	Expected Token (URL Encoded for GET)

	```HTML
	96yfUt3jgAIYx0o7i3tjprnBpotNO3Md%2Fyv%2BeToJ8qo%3D
	```

* **Error Codes**

	Please refer to HTTP response headers for correct error codes and messages as IIS may reformat or replace JSON responses with standard error templates.
