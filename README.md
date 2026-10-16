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
bzg install http
bzg run
```

Use Bonezegei v1.3.3 as specified by the laboratory instructions. The `http` package files are generated under `lib/` by `bzg install` and are intentionally not committed.

If `bzg run` prints usage information or the server reports that `run` is undefined, check `bonezegei -v` and install the required v1.3.3 runtime. Older builds may not provide the HTTP/WebSocket API used by this lab.

Open [http://localhost:8000](http://localhost:8000). Keep the terminal running while testing. To test multiple clients, open that address in two or more browser windows, connect, and send a message from one window. Every connected window, including the sender, should show the broadcast with the sender's client ID. Close a window and check the server terminal for its disconnect event.

Visit an unknown path such as [http://localhost:8000/not-found](http://localhost:8000/not-found) to see the custom 404 page.

## Project files

```text
.
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
├── app.bzg
├── package.json
└── public/
    ├── 404.html
    └── index.html
```

`app.bzg` logs HTTP requests, WebSocket connections, received messages, and disconnects. `public/index.html` is the browser chat client, and `public/404.html` is shown for non-root HTTP paths. The `.gitattributes` file asks GitHub Linguist to highlight `.bzg` files as JavaScript.

## Laboratory evidence

Capture screenshots for the report showing:

1. `bonezegei -v` reporting version 1.3.3.
2. Successful `bzg install` and the server running with `bzg run`.
3. Two browser windows connected, with a message broadcast visible in both.
4. The custom page displayed after visiting an unknown route.

## License

This project is available under the MIT License. See [LICENSE](LICENSE).
