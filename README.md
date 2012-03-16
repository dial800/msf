![Documentation](http://docs.dial800.com/images/roundtrip.png)

We know. You have two days to integrate with us. Don't worry, it's easy. We're here to help.

## How to submit data

* [if I am using PHP](#using-php)?
* [or C Sharp?](#using-c-sharp)
* [or Python?](#using-python)
* [or Ruby?](#using-ruby)

### Using PHP

```php
<?php

# 1. Generate Payload

$request = new HTTP_Request2('http://routing.dial800.com/roundtrip');
$request->setMethod(HTTP_Request2::METHOD_POST)
    ->setAuth('user','password', HTTP_Request2::AUTH_BASIC)
    ->setHeader('Content-type: application/roundtrip.sales')
    ->setBody(
        "<?xml version=\"1.0\" encoding=\"utf-8\"?>\r\n" .
        "<Call xmlns=\"http://www.dial800.com/roundtrip/2011-07-15\r\n" .
        "      xmlns:rs=\"http://www.dial800.com/roundtrip-sales/2011-08-04\">" .
        "   <ANI>tel:3105555555</ANI>\r\n" .
        "   <Target>tel:3109999999</Target>\r\n" . 
        "   <CallStart>2011-07-15T01:02:03-08:00</CallStart>\r\n" .
        "   <msf:ProductCode>PHD4</msf:ProductCode>\r\n" .
        "   <msf:MediaSource>KNBC</msf:MediaSource>\r\n" .
        "   <msf:CallerFirstName>John</msf:CallerFirstName>\r\n" .
        "   <msf:CallerMiddleName>Jerry</msf:CallerMiddleName>\r\n" .
        "   <msf:CallerLastName>Smith</msf:CallerLastName>\r\n" .
        "   <msf:CallerCity>Los Angeles</msf:CallerCity>\r\n" .
        "   <msf:CallerState>CA</msf:CallerState>\r\n" .
        "   <msf:CallerZipCode>90210</msf:CallerZipCode>\r\n" .
        "   <msf:OtherFirstName />\r\n" .
        "   <msf:OtherMiddleInitial />\r\n" .
        "   <msf:OtherLastName />\r\n" .
        "   <msf:OtherCity />\r\n" .
        "   <msf:OtherState />\r\n" .
        "   <msf:OtherZip />\r\n" .
        "   <msf:OtherAreaCode />\r\n" .
        "   <msf:OtherPhone />\r\n" .
        "   <msf:ScriptQ1-1 />\r\n" .
        "   <msf:Gender />\r\n" .
        "   <msf:ScriptQ1-3 />\r\n" .
        "   <msf:ScriptQ1-4 />\r\n" .
        "   <msf:InqReason />\r\n" .
        "   <msf:CallCode>11</msf:CallCode>\r\n" .
        "   <msf:ScriptQ10-2 />\r\n" .
        "   <msf:ScriptQ10-3 />\r\n" .
        "   <msf:ScriptQ10-4 />\r\n" .
        "   <msf:OrderAmount>89.97</msf:OrderAmount>\r\n" .
        "   <msf:ScriptQ30-1 />\r\n" .
        "   <msf:ScriptQ30-2 />\r\n" .
        "   <msf:SequenceID />\r\n" .
        "   <msf:DOB />\r\n" .
        "   <msf:OtherDOB />\r\n" .
        "   <msf:ScriptDate3 />\r\n" .
        "   <msf:Keycode />\r\n" .
        "   <msf:HitScreenDisp />\r\n" .
        "   <msf:MainOfferQty>1</msf:MainOfferQty>\r\n" .
        "   <msf:Upsell1 />\r\n" .
        "   <msf:Upsell2 />\r\n" .
        "   <msf:Upsell3 />\r\n" .
        "   <msf:Upsell4 />\r\n" .
        "   <msf:Upsell5 />\r\n" .
        "   <msf:Upsell6 />\r\n" .
        "   <msf:Upsell7 />\r\n" .
        "   <msf:Upsell8 />\r\n" .
        "   <msf:Upsell9 />\r\n" .
        "   <msf:Upsell10 />\r\n" .
        "   <msf:Upsell11 />\r\n" .
        "   <msf:Upsell12 />\r\n" .
        "   <msf:Upsell13 />\r\n" .
        "   <msf:Upsell14>0</msf:Upsell14>\r\n" .
        "</Call>"
    );

# 2. Submit

echo $request->send()->getBody();
?>
```

### Using C Sharp

```csharp
using System;
using System.IO;
using System.Net;
using System.Text;


namespace Dial800
{
    class Program
    {
        static void Main(string[] args)
        {
            byte[] postDataBytes;
            const string userName    = "user";
            const string password    = "password";
            const string contentType = "application/roundtrip.sales";
            const string postMethod  = "POST";
            const string postData    
            = @"<?xml version="1.0" encoding="utf-8" ?>
                <Call xmlns="http://www.dial800.com/roundtrip/2011-07-15"
                      xmlns:rs="http://www.dial800.com/roundtrip-sales/2011-08-04">      
                    <ANI>tel:3105555555</ANI>
                    <Target>tel:3109999999</Target>
                    <CallStart>2011-07-15T01:02:03-08:00</CallStart>
                    <msf:ProductCode>PHD4</msf:ProductCode>
                    <msf:MediaSource>KNBC</msf:MediaSource>
                    <msf:CallerFirstName>John</msf:CallerFirstName>
                    <msf:CallerMiddleName>Jerry</msf:CallerMiddleName>
                    <msf:CallerLastName>Smith</msf:CallerLastName>
                    <msf:CallerCity>Los Angeles</msf:CallerCity>
                    <msf:CallerState>CA</msf:CallerState>
                    <msf:CallerZipCode>90210</msf:CallerZipCode>
                    <msf:OtherFirstName />
                    <msf:OtherMiddleInitial />
                    <msf:OtherLastName />
                    <msf:OtherCity />
                    <msf:OtherState />
                    <msf:OtherZip />
                    <msf:OtherAreaCode />
                    <msf:OtherPhone />
                    <msf:ScriptQ1-1 />
                    <msf:Gender />
                    <msf:ScriptQ1-3 />
                    <msf:ScriptQ1-4 />
                    <msf:InqReason />
                    <msf:CallCode>11</msf:CallCode>
                    <msf:ScriptQ10-2 />
                    <msf:ScriptQ10-3 />
                    <msf:ScriptQ10-4 />
                    <msf:OrderAmount>89.97</msf:OrderAmount>
                    <msf:ScriptQ30-1 />
                    <msf:ScriptQ30-2 />
                    <msf:SequenceID />
                    <msf:DOB />
                    <msf:OtherDOB />
                    <msf:ScriptDate3 />
                    <msf:Keycode />
                    <msf:HitScreenDisp />
                    <msf:MainOfferQty>1</msf:MainOfferQty>
                    <msf:Upsell1 />
                    <msf:Upsell2 />
                    <msf:Upsell3 />
                    <msf:Upsell4 />
                    <msf:Upsell5 />
                    <msf:Upsell6 />
                    <msf:Upsell7 />
                    <msf:Upsell8 />
                    <msf:Upsell9 />
                    <msf:Upsell10 />
                    <msf:Upsell11 />
                    <msf:Upsell12 />
                    <msf:Upsell13 />
                    <msf:Upsell14>0</msf:Upsell14>
                </Call>";

            const string uri = "http://roundtrip.dial800.com/roundtrip";

            postDataBytes = Encoding.UTF8.GetBytes( postData );

            var urlEndpoint = new Uri(uri);
            var request = WebRequest.Create( urlEndpoint ) as HttpWebRequest;

            request.Credentials   = new NetworkCredential( userName, password );
            request.Method        = postMethod;
            request.ContentType   = contentType;
            request.ContentLength = postDataBytes.Length;

            using(Stream postStream = request.GetRequestStream())
            {
                postStream.Write( postDataBytes, 0, postDataBytes.Length );
            }

            try
            {
                using ( HttpWebResponse response = request.GetResponse() as HttpWebResponse )
                {
                    var reader = new StreamReader( response.GetResponseStream() );
                    Console.WriteLine( reader.ReadToEnd() );
                }
            }
            catch (WebException ex)
            {
                if (ex.Response != null)
                {
                    using (HttpWebResponse errorResponse = (HttpWebResponse)ex.Response)
                    {
                        Console.WriteLine(
                            "The server returned '{0}' with the status code {1} ({2:d}).",
                            errorResponse.StatusDescription, errorResponse.StatusCode,
                            errorResponse.StatusCode);
                    }
                }
            }
            Console.ReadKey();
        }
    }
}
```

### Using Python

```python
from requests.auth import HTTPBasicAuth
payload = '''
<?xml version="1.0" encoding="utf-8" ?>
<Call xmlns="http://www.dial800.com/roundtrip/2011-07-15"
      xmlns:rs="http://www.dial800.com/roundtrip-sales/2011-08-04">      
    <ANI>tel:3105555555</ANI>
    <Target>tel:3109999999</Target>
    <CallStart>2011-07-15T01:02:03-08:00</CallStart>
    <msf:ProductCode>PHD4</msf:ProductCode>
    <msf:MediaSource>KNBC</msf:MediaSource>
    <msf:CallerFirstName>John</msf:CallerFirstName>
    <msf:CallerMiddleName>Jerry</msf:CallerMiddleName>
    <msf:CallerLastName>Smith</msf:CallerLastName>
    <msf:CallerCity>Los Angeles</msf:CallerCity>
    <msf:CallerState>CA</msf:CallerState>
    <msf:CallerZipCode>90210</msf:CallerZipCode>
    <msf:OtherFirstName />
    <msf:OtherMiddleInitial />
    <msf:OtherLastName />
    <msf:OtherCity />
    <msf:OtherState />
    <msf:OtherZip />
    <msf:OtherAreaCode />
    <msf:OtherPhone />
    <msf:ScriptQ1-1 />
    <msf:Gender />
    <msf:ScriptQ1-3 />
    <msf:ScriptQ1-4 />
    <msf:InqReason />
    <msf:CallCode>11</msf:CallCode>
    <msf:ScriptQ10-2 />
    <msf:ScriptQ10-3 />
    <msf:ScriptQ10-4 />
    <msf:OrderAmount>89.97</msf:OrderAmount>
    <msf:ScriptQ30-1 />
    <msf:ScriptQ30-2 />
    <msf:SequenceID />
    <msf:DOB />
    <msf:OtherDOB />
    <msf:ScriptDate3 />
    <msf:Keycode />
    <msf:HitScreenDisp />
    <msf:MainOfferQty>1</msf:MainOfferQty>
    <msf:Upsell1 />
    <msf:Upsell2 />
    <msf:Upsell3 />
    <msf:Upsell4 />
    <msf:Upsell5 />
    <msf:Upsell6 />
    <msf:Upsell7 />
    <msf:Upsell8 />
    <msf:Upsell9 />
    <msf:Upsell10 />
    <msf:Upsell11 />
    <msf:Upsell12 />
    <msf:Upsell13 />
    <msf:Upsell14>0</msf:Upsell14>
</Call>
'''
r = request.post('http://routing.dial800.com/routing',
                 auth=HTTPBasicAuth('user','password'),
                 headers={'content-type': 'application/roundtrip.sales'},
                 data=payload)
```

### Using Ruby

```ruby
require "net/http"
require "uri"

uri = URI.parse("http://routing.dial800.com/routing")

http         = Net::HTTP.new(uri.host, uri.port)
request      = Net::HTTP::Post.new(uri.host,uri.port)
request.body = xml_string
request.basic_auth("user","password")
request.content_type = "application/roundtrip.sales"
response     = http.request(request)
```

## Reference

### Authentication

### POST

#### Request

```
POST /calls
Content-Type: application/mercury.shortform
```

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Call xmlns="http://www.dial800.com/roundtrip/2011-07-15"
      xmlns:msf="http://www.mercurymedia.com/shortform/2011-07-15">      
    <ANI>tel:3105555555</ANI>
    <Target>tel:3109999999</Target>
    <CallStart>2011-07-15T01:02:03-08:00</CallStart>
    <msf:ProductCode>PHD4</msf:ProductCode>
    <msf:MediaSource>TV</msf:MediaSource>
    <msf:CallerFirstName>John</msf:CallerFirstName>
    <msf:CallerMiddleName>Jerry</msf:CallerMiddleName>
    <msf:CallerLastName>Smith</msf:CallerLastName>
    <msf:CallerCity>Los Angeles</msf:CallerCity>
    <msf:CallerState>CA</msf:CallerState>
    <msf:CallerZipCode>90210</msf:CallerZipCode>
    <msf:OtherFirstName />
    <msf:OtherMiddleInitial />
    <msf:OtherLastName />
    <msf:OtherCity />
    <msf:OtherState />
    <msf:OtherZip />
    <msf:OtherAreaCode />
    <msf:OtherPhone />
    <msf:ScriptQ1-1 />
    <msf:Gender />
    <msf:ScriptQ1-3 />
    <msf:ScriptQ1-4 />
    <msf:InqReason />
    <msf:CallCode>11</msf:CallCode>
    <msf:ScriptQ10-2 />
    <msf:ScriptQ10-3 />
    <msf:ScriptQ10-4 />
    <msf:OrderAmount>89.97</msf:OrderAmount>
    <msf:ScriptQ30-1 />
    <msf:ScriptQ30-2 />
    <msf:SequenceID />
    <msf:DOB />
    <msf:OtherDOB />
    <msf:ScriptDate3 />
    <msf:Keycode />
    <msf:HitScreenDisp />
    <msf:MainOfferQty>1</msf:MainOfferQty>
    <msf:Upsell1 />
    <msf:Upsell2 />
    <msf:Upsell3 />
    <msf:Upsell4 />
    <msf:Upsell5 />
    <msf:Upsell6 />
    <msf:Upsell7 />
    <msf:Upsell8 />
    <msf:Upsell9 />
    <msf:Upsell10 />
    <msf:Upsell11 />
    <msf:Upsell12 />
    <msf:Upsell13 />
    <msf:Upsell14 />
</Call>
```

#### Response

Call successfully matched.

```xml
200 OK
<ID>XDhshURwv60Q2nRyN4cnGVCmMB1cP</ID>
```

No match for the call.

```
404 Not Found
```

### PUT

```
PUT /calls
Content-Type: application/mercury.shortform
```

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Call xmlns="http://www.dial800.com/roundtrip/2011-07-15"
      xmlns:msf="http://www.mercurymedia.com/shortform/2011-07-15">      
    <ID>12345678990</ID>
    <msf:ProductCode>PHD4</msf:ProductCode>
    <msf:MediaSource>TV</msf:MediaSource>
    <msf:CallerFirstName>John</msf:CallerFirstName>
    <msf:CallerMiddleName>Jerry</msf:CallerMiddleName>
    <msf:CallerLastName>Smith</msf:CallerLastName>
    <msf:CallerCity>Los Angeles</msf:CallerCity>
    <msf:CallerState>CA</msf:CallerState>
    <msf:CallerZipCode>90210</msf:CallerZipCode>
    <msf:OtherFirstName />
    <msf:OtherMiddleInitial />
    <msf:OtherLastName />
    <msf:OtherCity />
    <msf:OtherState />
    <msf:OtherZip />
    <msf:OtherAreaCode />
    <msf:OtherPhone />
    <msf:ScriptQ1-1 />
    <msf:Gender />
    <msf:ScriptQ1-3 />
    <msf:ScriptQ1-4 />
    <msf:InqReason />
    <msf:CallCode>11</msf:CallCode>
    <msf:ScriptQ10-2 />
    <msf:ScriptQ10-3 />
    <msf:ScriptQ10-4 />
    <msf:OrderAmount>89.97</msf:OrderAmount>
    <msf:ScriptQ30-1 />
    <msf:ScriptQ30-2 />
    <msf:SequenceID />
    <msf:DOB />
    <msf:OtherDOB />
    <msf:ScriptDate3 />
    <msf:Keycode />
    <msf:HitScreenDisp />
    <msf:MainOfferQty>1</msf:MainOfferQty>
    <msf:Upsell1 />
    <msf:Upsell2 />
    <msf:Upsell3 />
    <msf:Upsell4 />
    <msf:Upsell5 />
    <msf:Upsell6 />
    <msf:Upsell7 />
    <msf:Upsell8 />
    <msf:Upsell9 />
    <msf:Upsell10 />
    <msf:Upsell11 />
    <msf:Upsell12 />
    <msf:Upsell13 />
    <msf:Upsell14 />
</Call>
```

#### Response

Call successfully matched.

```xml
200 OK
<ID>12345678990</ID>
```

No match for the call.

```
404 Not Found
```

## Other integrations

### Dial800

[Our native interface](http://docs.dial800.com/).

### MercuryMedia

[Mercury Long Form](http://docs.dial800.com/dial800/mlf).

### Euro

Are you using Euro's format? You can find the details [here](http://docs.dial800.com/dial800/euro).