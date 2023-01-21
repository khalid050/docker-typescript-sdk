<h2>Getting started</h2>


```bash
npm install @plswork/docker-typescript-client
```


```javascript
const { Docker } = require("@plswork/docker-typescript-client");

const { Container, Image } = new Docker();
/**
 *  Defaults: 
 *    url: "http://localhost/v1.41/"
 *    socketPath: "/var/run/docker.sock"
 */

// Override defaults
const { Container, Image } = new Docker({ url: my_url, socketPath: my_socket_path });

const imageTag = "myubuntuimage";
await Image.build(`${process.cwd()}/path/to/tar/archive`, {
  t: imageTag,
});

const myContainer = await Container.create({
  containerName: "mynewcontainer",
  defaultCommand: ["echo", "hello"],
});
```
