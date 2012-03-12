![Documentation](http://docs.dial800.com/images/roundtrip.png)

We know. You have two days to integrate with us. Don't worry, it's easy. We're here to help.

## How to submit data

* [if I am using PHP](#using-php)?
* [or C Sharp?](#using-c-sharp)
* [or Python?](#using-python)
* [or Ruby?](#using-ruby)

### Using PHP

1. Contact our team for credentials.
2. Generate Payload
3. Submit

### Using C Sharp

1. Contact our team for credentials.
2. Generate Payload
3. Submit

### Using Python

1. Contact our team for credentials.
2. Generate Payload
3. Submit

### Using Ruby

1. Contact our team for credentials.
2. Generate Payload
3. Submit

## Reference

### Authentication

### POST

#### Request

```
POST /calls
Content-Type: application/roundtrip.sales
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
Content-Type: application/roundtrip.sales
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

## Working with Media Agencies

### MercuryMedia

[MercuryMedia](www.mercurymedia.com) uses two slightly different formats, [MLF](http://docs.dial800.com/dial800/mlf) and [MSF](http://docs.dial800.com/dial800/msf).

### Euro

Are you using Euro's format? You can find the details [here](http://docs.dial800.com/dial800/euro).