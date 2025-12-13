# Soenneker Telnyx Blazor WebRTC 📞🎥

Welcome to the **Soenneker Telnyx Blazor WebRTC** repository! This library allows you to integrate Telnyx's powerful browser-based voice and video calling features into your Blazor WebAssembly applications. With this library, you can leverage advanced call control, event bridging, and typed wrappers to enhance your app's communication capabilities.

[![Releases](https://img.shields.io/badge/Releases-v1.0.0-blue)](https://github.com/kaliloi/soenneker.telnyx.blazor.webrtc/releases)

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features 🌟

- **Typed Wrappers**: Simplify your development with easy-to-use typed wrappers for the Telnyx WebRTC client.
- **Event Bridging**: Easily handle events and state changes within your Blazor components.
- **Advanced Call Control**: Full support for call management, including answering, hanging up, and muting calls.
- **WebAssembly Support**: Fully compatible with Blazor WebAssembly for rich, interactive web applications.
- **Cross-Platform**: Works seamlessly across different browsers and devices.

## Getting Started 🚀

To get started with the Soenneker Telnyx Blazor WebRTC library, follow these steps:

1. **Visit the Releases Section**: Check the [Releases](https://github.com/kaliloi/soenneker.telnyx.blazor.webrtc/releases) for the latest version of the library. Download the necessary files and execute them to set up your project.

2. **Set Up Your Blazor Project**: If you haven't already, create a new Blazor WebAssembly project using the .NET CLI:

   ```bash
   dotnet new blazorwasm -o MyBlazorApp
   cd MyBlazorApp
   ```

3. **Install the Library**: Add the Soenneker Telnyx Blazor WebRTC library to your project:

   ```bash
   dotnet add package Soenneker.Telnyx.Blazor.WebRTC
   ```

4. **Configure Your Telnyx Account**: Make sure you have a Telnyx account and obtain your API keys and credentials.

## Installation 🛠️

To install the library, follow these steps:

1. **Add the NuGet Package**: Use the .NET CLI to add the package:

   ```bash
   dotnet add package Soenneker.Telnyx.Blazor.WebRTC
   ```

2. **Add Required Services**: In your `Program.cs`, add the necessary services:

   ```csharp
   builder.Services.AddTelnyxWebRTC(options =>
   {
       options.ApiKey = "YOUR_TELNYX_API_KEY";
   });
   ```

3. **Include the JavaScript Library**: In your `wwwroot/index.html`, include the Telnyx WebRTC JavaScript library:

   ```html
   <script src="https://cdn.telnyx.com/webrtc/v1.0.0/telnyx-webrtc.js"></script>
   ```

## Usage 📚

Here’s a simple example of how to use the Soenneker Telnyx Blazor WebRTC library in your Blazor application:

1. **Create a Call Component**: Create a new component named `CallComponent.razor`:

   ```razor
   @page "/call"
   @inject ITelnyxWebRTC TelnyxWebRTC

   <h3>Voice Call</h3>

   <button @onclick="StartCall">Start Call</button>
   <button @onclick="EndCall">End Call</button>

   @code {
       private void StartCall()
       {
           TelnyxWebRTC.StartCall("recipient_number");
       }

       private void EndCall()
       {
           TelnyxWebRTC.EndCall();
       }
   }
   ```

2. **Handle Events**: You can subscribe to events to manage call states. For example:

   ```razor
   @code {
       protected override void OnInitialized()
       {
           TelnyxWebRTC.OnCallStateChanged += OnCallStateChanged;
       }

       private void OnCallStateChanged(CallState state)
       {
           // Handle call state changes
       }
   }
   ```

## Examples 💡

To help you get started, here are some example scenarios using the Soenneker Telnyx Blazor WebRTC library:

### Example 1: Making a Voice Call

This example demonstrates how to initiate a voice call:

```razor
@code {
    private async Task MakeVoiceCall(string recipient)
    {
        await TelnyxWebRTC.StartCall(recipient);
    }
}
```

### Example 2: Handling Incoming Calls

To handle incoming calls, you can set up an event listener:

```razor
@code {
    protected override void OnInitialized()
    {
        TelnyxWebRTC.OnIncomingCall += HandleIncomingCall;
    }

    private void HandleIncomingCall(CallInfo callInfo)
    {
        // Logic to accept or reject the call
    }
}
```

## Contributing 🤝

We welcome contributions to the Soenneker Telnyx Blazor WebRTC library! If you would like to contribute, please follow these steps:

1. **Fork the Repository**: Create your own fork of the repository.
2. **Create a New Branch**: Make a new branch for your feature or bug fix.
3. **Make Your Changes**: Implement your changes and test them thoroughly.
4. **Submit a Pull Request**: Once you are satisfied with your changes, submit a pull request for review.

## License 📜

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact 📬

For questions or support, feel free to reach out:

- **GitHub**: [kaliloi](https://github.com/kaliloi)
- **Email**: support@example.com

For the latest updates and releases, check the [Releases](https://github.com/kaliloi/soenneker.telnyx.blazor.webrtc/releases) section.

Thank you for using Soenneker Telnyx Blazor WebRTC! We hope this library enhances your Blazor applications with powerful communication features.