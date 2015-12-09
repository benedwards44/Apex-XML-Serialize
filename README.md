# Apex-XML-Serialize
Utility class for serializing a single or list of sObjects or Apex Classes object to a XML string. The goal is to mimic functionality of the standard JSON.serialize() method.

## Usage
To serialize an object into XML string, call the ```serialize(objectToSerialize, NameOfTopLevel)``` method by passing it the object or list of objects to serialize and the name of the top-level XML wrapper.

### Single Object
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
    <Name>Ben Edwards Ltd</Name>
</Account>
```

### Array of Objects
```
// Query for an Account records
List<Account> accounts = [Select Id, Name From Account];

// Call the method to serialize the object
String xmlString = XmlUtility.serialize(accounts, 'Accounts');
```
Returns:
```
<Accounts>
    <Account>
        <attributes>
            <type>Account</type>
            <url>/services/data/v35.0/sobjects/Account/00128000002PMvhAAG</url>
        </attributes>
        <Id>00128000002PMvhAAG</Id>
        <Name>Ben Edwards Ltd</Name>
    </Account>
    <Account>
        <attributes>
            <type>Account</type>
            <url>/services/data/v35.0/sobjects/Account/00128000002PMvhAAH</url>
        </attributes>
        <Id>00128000002PMvhAAH</Id>
        <Name>Ben Enterprises Global Worldwide Ltd</Name>
    </Account>
</Accounts>
```

