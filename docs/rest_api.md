#REST API Specification

!!! caution 
    Many API GET requests in BHR can be extremely slow, especially when accessing via a web browser, 
    due to the number of entries in the block lists. 
    Unless you have a specific reason for querying the entire block list, 
    it is recommend limiting the use of GET functions unless necessary.
    
Below is the API specification for several important functions in BHR. bhr-client actually provides python functions to interface directly with the "block" API calls. 
However, you may find it necessary, or simply easier to make the calls yourself. **In short...try using bhr-client's built in functions or cli before resorting to these calls.**

Functions for whitelisting are not provided by bhr-client, so these calls SHOULD be used directly.

## POST /block (undocumented)

Adds a BHR block entry to database and submits a block via BGP

### POST Parameters

!!! warning
    THE 'skip_whitelist' PARAMETER IS DANGEROUS. DON'T SET THIS TO "TRUE" UNLESS YOU HAVE A VERY GOOD REASON.

| Name           | Description                                                                  | Type    | Additional Information |
| -------------- | ---------------------------------------------------------------------------- | ------- | ---------------------- |
| autoscale      | Whether or not to auto scale the duration based on server side block history | Boolean | Not required           |
| cidr           | CIDR representation of host or subnet to block                               | String  | Required               |
| duration       | Duration to blackhole in seconds                                             | Integer | Required               |
| extend         | Whether or not to restart block counter is host is already blocked           | Boolean | Not required           |
| skip_whitelist | Whether or not to bypass the server side whitelist                           | Boolean | Not required           |
| source         | Source of the block                                                          | String  | Required               |
| why            | Reason for blackholing IP address                                            | String  | Required               |

### Sample

    {
        "cidr": "194.88.106.29",
        "source": "api",
        "why": "doing bad things",
        "duration": 3600,
        "autoscsale": False,
        "extend": False
    }


## POST /mblock (undocumented)

Adds multiple BHR block entry in one post and submits a block via BGP

### POST Parameters

| Name | Description              | Type | Additional Information                        |
| ---- | ------------------------ | ---- | --------------------------------------------- |
| None | Array of "block" entries | List | Required. See "POST /block" for entry format. |


### Sample

    [
        {
            "cidr": "194.88.106.29",
            "source": "api",
            "why": "doing bad things",
            "duration": 3600,
        },
        {
            "cidr": "194.88.106.30",
            "source": "api",
            "why": "doing other bad things",
            "duration": 3600,
        },
        ...
    ]
    
        
## POST /whitelist
 
Adds a whitelist entry to BHR
 
### POST parameters
 
| Name | Description                                        | Type   | Additional Information |
| ---- | -------------------------------------------------- | ------ | ---------------------- |
| cidr | CIDR representation of host or subnet to whitelist | String | Required               |
| why  | Reason for whitelisting IP address                 | String | Required               |
 
### Sample
    {
        "cidr": "10.0.0.0/8",
        "why": "Private IP address space"
    }
    
## DELETE /whitelist/{id}

Deletes a whitelist entry from BHR

### URI Parameters

| Name | Description                                   | Type    | Additional Information |
| ---- | --------------------------------------------- | ------- | -----------------------|
| id   | Global unique identifier of whitelist element | Integer | Required               |