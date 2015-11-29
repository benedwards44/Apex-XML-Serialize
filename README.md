# Apex-XML-Serialize
Utility class for serializing a sObject or Apex Class object to a XML string

## Usage
To serialize an object into XML string, call the ```serialize()``` method by passing it the object to serialize and the name of the top-level XML wrapper. Eg.

```
// Query for an Account record
Account account = [Select Id, Name From Account Limit 1];

// Call the method to serialize the object
String xmlString = XmlUtility.serialize(account, 'Account');
```
Returns:
```
<Account>
    <attributes>
        <type>Account</type>
        <url>/services/data/v35.0/sobjects/Account/00128000002PMvhAAG</url>
    </attributes>
    <Id>00128000002PMvhAAG</Id>
    <Name>Therapeutic Research Center</Name>
</Account>
```

