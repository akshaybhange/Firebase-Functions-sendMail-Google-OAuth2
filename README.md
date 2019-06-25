# Firebase Functions Send Email using Google OAuth2
Send email through firebase functions with Node.js using Google's OAuth2, Nodemailer, SMTP & Gmail 

### Instructions to Setup OAuth2
Please follow [my article on Medium](https://medium.com/@akshay.bhange/firebase-functions-send-email-using-google-oauth2-20c552da6b3e) for OAuth2 setup


### Calling function from Android APP
```
addMessage("to.email.here@domain.com")

private fun addMessage(text: String): Task<String> {
        val data = hashMapOf(
            "text" to text,
            "push" to true
        )
        val functions = FirebaseFunctions.getInstance()
        return functions
            .getHttpsCallable("sendemail")
            .call(data)
            .continueWith {
                it.result?.data as String
            }
    }
```

### For other platfroms and more details
Please follow [official documentation](https://firebase.google.com/docs/functions/callable#call_the_function) for other platforms