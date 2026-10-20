# ITE183 Laboratory 2: WebSocket Server

A small multi-client chat application built with Bonezegei Scripting Language (BSL) v1.3.3. The HTTP server serves the chat page on port `8000`, upgrades browser connections to WebSockets, and broadcasts messages to every connected client.

## Requirements

- Bonezegei v1.3.3
- A modern browser with WebSocket support

Check the installed version:

```powershell
bonezegei -v
```

On Windows, install or update Bonezegei through Microsoft Store. On Linux, download the release package from the [Bonezegei Scripting Language repository](https://github.com/bonezegei/Bonezegei_Scripting), install it with `sudo apt install ./Bonezegei-x86.deb`, then run `bonezegei -v`.

## Install and run

From the project directory, install the HTTP package used by `app.bzg` and then start the server:

```sh
bzg install
bzg run
```

Use Bonezegei v1.3.3 as specified by the laboratory instructions. The `http` package files are generated under `lib/` by `bzg install` and are intentionally not committed.

If `bzg run` prints usage information or the server reports that `run` is undefined, check `bonezegei -v` and install the required v1.3.3 runtime. Older builds may not provide the HTTP/WebSocket API used by this lab.

Open [http://localhost:8000](http://localhost:8000). Keep the terminal running while testing. To test multiple clients, open that address in two or more browser windows, connect, and send a message from one window. Each broadcast appears once in every connected window. Your messages show **You** on the right; other clients see your display name on the left. Close a window and check the server terminal for its disconnect event.

Click the profile in the sidebar or the avatar in the top bar to change your display name and choose one of five avatars: Orbit, Ember, Luna, Nova, or Sprout. Profile and light/dark theme preferences are saved in browser local storage. Set different names in the two test windows before sending messages. Changes apply to future messages; profiles are not authenticated accounts. Reconnect and clear-local-messages controls are also available.

Visit an unknown path such as [http://localhost:8000/bksdjfs](http://localhost:8000/bksdjfs) to see the custom 404 page.

Unknown routes return the custom page with HTTP status `404 Not Found`. Chat history is not stored on the server and clears on reload.

## Laboratory report and captured evidence

The [Word report](documentation/ITE183_Lab2_WebSocket_Report.docx) contains the implementation explanation, verification evidence, test results, and limitations. The report includes Perlan Jubay as the student name. Complete the section and instructor fields before submission.

- [Evidence images](documentation/screenshots/) show the v1.3.3 version, dependency installation, server startup, custom 404 page, and a combined two-client chat capture. The chat capture shows Ember and Sprout exchanging four messages in both browser windows.
- [Evidence files](documentation/evidence/) include command output and browser test results matching the verified Ember and Sprout session.
- Public repository: [PerLanDo/ITE183_Lab2_Websocket](https://github.com/PerLanDo/ITE183_Lab2_Websocket).

Commit and push the current source and documentation before submitting the repository link.

## Project files

```text
.
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
├── app.bzg
├── package.json
├── documentation/
    ├── ITE183_Lab2_WebSocket_Report.docx
    ├── evidence/
    └── screenshots/
└── public/
    ├── 404.html
    └── index.html
```

`app.bzg` logs HTTP requests, WebSocket connections, received messages, and disconnects. `public/index.html` is the browser chat client, and `public/404.html` is shown for non-root HTTP paths. The `.gitattributes` file asks GitHub Linguist to highlight `.bzg` files as JavaScript.

## Included laboratory evidence

The `documentation/screenshots/` folder contains:

1. `01-version.png` — `bonezegei -v` reporting version 1.3.3.
2. `02-install.png` — successful `bzg install` of the HTTP dependency.
3. `03-server-startup.png` — server startup output and event logs showing connections, routes, and message exchange between Ember and Sprout.
4. `04-custom-404.png` — the custom page displayed for an unknown route.
5. `05-Chat.png` — both connected browser clients showing the same four-message exchange.

## License

This project is available under the MIT License. See [LICENSE](LICENSE).
