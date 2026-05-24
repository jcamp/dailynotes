## JC Daily Log 20260523

### WordPress Playground (temp WordPress site for testing)

https://wordpress.org/playground/
Docs: https://wordpress.github.io/wordpress-playground/

WordPress in one click

WordPress Playground is the platform that lets you run WordPress instantly on any device without a host. It’s your place to build, experiment, test, and grow.

#### WordPress Playground Website

[https://playground.wordpress.net/](https://playground.wordpress.net/) is a versatile tool that allows developers to run WordPress in a browser without needing a server. 
This environment is particularly useful for testing plugins, themes, and other WordPress features quickly and efficiently.

#### Playground CLI

[@wp-playground/cli](https://www.npmjs.com/package/@wp-playground/cli) is a command-line tool that simplifies the WordPress development and testing flow. 
It provides a quick and easy way to set up a local WordPress environment with minimal configuration.

##### Key Features:

- **Quick Setup**: Set up a local WordPress environment in seconds with minimal configuration, just a compatible Node version is needed.
- **Flexibility**: Allows for configuration to adapt to different scenarios.

##### How to use it:

Use `npx` to run the Playgroud CLI anywhere:

```
   npx @wp-playground/cli@latest server
```

Open the provided local URL in your browser to start using WordPress. For themes and plugin developers, use the `--auto-mount` flag to test your plugins or themes:

```
  cd my-plugin-or-theme-directory
  npx @wp-playground/cli@latest server --auto-mount
```

### Test Our Brand New PHP Playground
This sandbox lets you write, test, and debug code directly from the client-side, which enables instant, shareable, and safe code prototyping in a way that wasn’t previously possible.

[Go to PHP playground](https://playground.wordpress.net/php-playground.html)

### Hosting your own Playground on your servers

https://wordpress.github.io/wordpress-playground/developers/architecture/host-your-own-playground/

Host your own Playground

You can host the Playground on your own domain instead of playground.wordpress.net.

This is useful for having full control over its content and behavior, as well as removing dependency on a third-party server. 
It can provide a more customized user experience, for example: a playground with preinstalled plugins and themes, default site settings, or demo content.

## Usage[​](https://wordpress.github.io/wordpress-playground/developers/architecture/host-your-own-playground/#usage "Direct link to Usage")

A self-hosted Playground can be embedded as an iframe.

```
<iframe src="https://my-playground.com"></iframe>
```

Or dynamically loaded by passing the remote URL to the [Playground Client](https://wordpress.github.io/wordpress-playground/developers/apis/javascript-api/playground-api-client).

```
import { startPlaygroundWeb } from '@wp-playground/client';

const client = await startPlaygroundWeb({
	iframe: document.getElementById('wp'),
	remoteUrl: `https://my-playground.com/remote.html`,
});
```
