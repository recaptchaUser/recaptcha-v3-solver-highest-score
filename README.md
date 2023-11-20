# ReCaptcha-V3-Solver-0.7-0.9-Scores
# Solve reCaptcha v3 with the highest token score 0.7-0.9
Prior to embarking on the process of resolving reCaptcha v3, it is essential to ascertain with certainty that we are indeed dealing with reCaptcha v3 as opposed to a different version of reCaptcha.

How can one determine this with confidence? We offer a highly user-friendly browser extension that excels in identifying not only the version of any reCaptcha but also its various parameters with impeccable accuracy—guaranteed at 100%. You can visualize the extension and its identification prowess here:
![](https://assets.capsolver.com/prod/images/post/2023-11-06/39f8b6f8-0657-426c-80a5-29fa7719e459.png)
For detailed instructions on how to utilize this extension to detect reCaptcha and its specific parameters, please refer to the following link: [Instruction Manual for reCaptcha Identification Extension](https://www.capsolver.com/blog/Extension/identify-any-captcha-and-parameters)

Once confirmation of the presence of reCaptcha v3 is established and you have successfully retrieved the Capsolver JSON, please proceed by copying the provided JSON data:

![](https://assets.capsolver.com/prod/images/post/2023-11-06/214695f4-2dda-4eb7-86fd-b9bcbf18898d.png)


## Strategies for Solving reCaptcha with Scores Between 0.7 and 0.9
Upon obtaining the Capsolver JSON, the content should resemble the following structure:


```json
POST https://api.capsolver.com/createTask
Host: api.capsolver.com
Content-Type: application/json
{
    "clientKey": "YOUR_API_KEY",
    "task": {
        "type": "ReCaptchaV3TaskProxyLess",
        "websiteURL": "https://example.com",
        "websiteKey": "6LcR_okUAAAAAPYrPe-HK_0RULO1aZM15ENyM-Mf",
        "anchor": "value",
        "reload": "value",
        "pageAction": "homepage"
    }
}
```
You are encouraged to initially attempt the `ReCaptchaV3TaskProxyLess` to verify if the token functions as intended. In the event of a failure, it is advisable to try the `ReCaptchaV3Task` task type, integrating your personal proxy into the process.

Should difficulties persist, consider employing the `ReCaptchaV3M1TaskProxyLess` task type. This alternative comes equipped with high-caliber, built-in proxies, offering a more stable likelihood of achieving a score of 0.7 or higher.

## Procedure for Obtaining the Result
Once you have executed the creation of the task, you may retrieve the result by structuring your request as shown below:
```json
POST https://api.capsolver.com/getTaskResult
Host: api.capsolver.com
Content-Type: application/json
{
    "clientKey":"YOUR_API_KEY",
    "taskId": "37223a89-06ed-442c-a0b8-22067b79c5b4" //ID created by the createTask method
}
```
