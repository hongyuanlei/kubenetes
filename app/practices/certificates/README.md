# Create a Self-Signed Root CA

Read doc: https://www.baeldung.com/openssl-self-signed-cert#1-create-a-self-signed-root-ca

```shell
openssl req -x509 -sha256 -days 1825 -newkey rsa:2048 -keyout rootCA.key -out rootCA.crt
```

Encode Certificate and Key:
```shell
base64 -w 0 < tls.crt > tls.crt.base64
base64 -w 0 < tls.key > tls.key.base64
```
