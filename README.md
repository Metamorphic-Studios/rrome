![Rrome Logo](/logo.png)


## TODO explantion of rrome as a system


## Rrome forms

Within Rrome you defined your own custom form types that you want to use within your system,
these are the primary way that you interface with your Rrome instance, allowing you to view
and change the information that it's linked to. Rrome forms are defined with JSON objects and
must have the following structure:
```
{
  id: String
  name: String
  model: []
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
An array of keys, as per the 'id', used for the displaying of stored data

## Rrome models
