# AppInsightInstrumentation

Steps to add App Insights telemetry to asp.net core application from Visual Studio

1. Open your project in Visual Studio.

2. Go to Project > Add Application Insights Telemetry.

3. Select Azure Application Insights > Next.

4. Choose your subscription and Application Insights instance. Or you can create a new instance with Create new. Select Next.

5. Add or confirm your Application Insights connection string. It should be prepopulated based on your selection in the previous step. Select Finish.

6. After you add Application Insights to your project, check to confirm that you're using the latest stable release of the SDK. Go to Project > Manage NuGet Packages > Microsoft.ApplicationInsights.AspNetCore. If you need to, select Update.

This will add the line below in Program.cs file 

**builder.Services.AddApplicationInsightsTelemetry(builder.Configuration["APPLICATIONINSIGHTS_CONNECTION_STRING"]);**

To view the data, go to the Application Insights on Azure Portal and you should be able to see the data flowing. You can view in the "Performance" tab or "Live Metrics"

<img width="755" alt="image" src="https://github.com/Kruthiv/AppInsightInstrumentation/assets/109948637/09cbb911-4b21-4a07-94cf-874b89c9a986">


In order to capture logs, use the ILogger capabilty. 
In this example, we have added the line below in SampleAppInstrumentation.cs where WeatherForecastUJ is the user journey name to capture User Journey details

**_logger.LogInformation("WeatherForecastUJ - Get Weather Forecast");**

To view the logs use traces table 

<img width="694" alt="image" src="https://github.com/Kruthiv/AppInsightInstrumentation/assets/109948637/d7ac040f-6b53-4e06-9720-1487b7c1b7e1">
