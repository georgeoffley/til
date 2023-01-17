# Testing `sendRequest` call in Postman

---
## Docs and Source
[Source Here](https://learning.postman.com/docs/sending-requests/grpc/postman-sandbox-api/#sending-http-request-from-scripts)

---
## Explanation and Notes
This API function is for sending a request within a Postman script. This is useful for creating calls and running tests against those calls.

*Note:
You need to make sure you put the error before the response in the callback args. Otherwise, it errors out. Example below*

---
## Code Example

```JavaScript
pm.sendRequest(postLedgerEntryBadIdRequest, function(error, response) {
    const jsonRespBadId = response.json();

    pm.test('PostLedgerUpdate should return error when resident is not found', function() {
        pm.expect(response).to.not.be.ok;
    })
})
```


#GeneralTools 
	#postman