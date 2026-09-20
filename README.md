## Azure Service Bus Use Case

This repository contains a C# automation project for validating Azure Service
Bus queue resources through the Azure portal. The project uses .NET Framework
4.8, NUnit, Selenium WebDriver, and the Page Object Model.

## What It Covers

- Signs in to the Azure portal using configuration-based test data.
- Navigates to Azure resources and locates the target Service Bus resource.
- Reads the queue message count and verifies that messages are available.
- Provides an `AzureServiceBusQueueSender` utility for sending messages to a
	queue using the Microsoft Azure Service Bus client library.

## Project Structure

```text
Configuration/     Application settings and environment placeholders
Core/              Shared test classes and Azure Service Bus utilities
Pages/             Azure portal page objects and navigation
TestData/          Configuration-backed credential access
TestScenarios/     NUnit test scenarios
```

## Requirements

- Windows
- Visual Studio with .NET Framework 4.8 developer tools
- Google Chrome
- ChromeDriver compatible with the installed Chrome version
- Access to an Azure subscription and the target Service Bus resource

## Configuration

Update `Configuration/App.config` for your local environment. The repository
contains placeholders only:

```xml
<add key="MicrosoftEmail" value="ENTER_AZURE_USERNAME" />
<add key="MicrosoftPassword" value="ENTER_AZURE_PASSWORD" />
<add key="ConString" value="ENTER_CONNECTION_STRING" />
<add key="QName" value="ENTER_QUEUE_NAME" />
<add key="ResourceName" value="ENTER_RESURCE_NAME" />
```

Do not commit real passwords, connection strings, access keys, or other
secrets. Use a local configuration mechanism or secret store for credentials.

## Run the Tests

1. Open `Azure-servicebus-usecase.sln` in Visual Studio.
2. Restore the NuGet packages.
3. Set the required values in `Configuration/App.config`.
4. Build the solution.
5. Run the NUnit tests from Test Explorer.

The main scenario is `ValidateServiceBusSendMessages`, which signs in to the
Azure portal and verifies that the selected Service Bus queue has a message
count greater than zero.


