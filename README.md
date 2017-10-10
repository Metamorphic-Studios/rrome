![Rrome Logo](/logo.png)


## TODO explantion of rrome as a system


## Rrome forms

Within Rrome you defined your own custom form types that you want to use within your system,
these are the primary way that you interface with your Rrome instance, allowing you to view
and change the information that it's linked to. Rrome forms are defined with JSON objects and
must have the following structure:
```
{
  id: String,
  name: String,
  model: [[]],
  display_keys: [String]
}
```

#### 'id' - STRING
A unique indentifier string for identifying the model.

#### 'name' - STRING
The human equivalent of the 'id', what you want this model be called.

#### 'model' - Array
A 2d array which stores much of the data contained within a rrome Model in the form 
of 'models', which themselves are JSON objects.

#### 'display_keys' - Array
An array of keys, as per the 'id', used for the displaying of stored data.


## Rrome models
Models are the internal data types stored within the Rrome forms and contain much of the 
information that informs both what data is displayed and the manner by which it is.
These models are defined using the following JSON object structure:
```
{
  label: String,
  id: String,
  type: ModelType,
  meta-type: JSON/Array
}
```

#### 'label' - String
The label of your model is functionally the same as the 'name' of the form,
a human-readable thing that you use for display and reference purposes.

#### 'id' - String
Again, much as with the form, the 'id' is used for server-side reference and identification
of the model in question.

#### 'meta-type' - JSON/Array
Based on the meta-type of the model the meta-type will define some extra configuration details
for passing down or for the direct display/collection of data.

#### 'type' - ModelType
The 'type' field of a Rrome model is the key for the kind of component that the given data of the
model will be displayed in, additionally may impose restraints upon what kind of data may be stored
within it. Rrome ships with a variety of pre-built types for use however made-for-purpose types are
entirely compatable with Rrome.

## Pre-build types:

|Type|Description|
|--|--|
|TEXT|Text input|
|DATE|Date input|
|LIST|List of objects|
|FSELECT|Foreign selector|
|FLIST|List of foreign objects|

#### TEXT/DATE
Text and Date types both simply construct components for text input or date input

##### FSELECT
```
meta-type: {
   id: String - Model id to select from
   display_keys: Array - Keys to display from model
}
```

##### LIST
```
meta-type: [
   {
      type: ModelType,
      label: String 
   }
]
```

##### FLIST
```
meta-type: {
   id: String - Model id to select from
   list_display: Keys to display in list
   display_keys: Keys to display in selector
}
```
