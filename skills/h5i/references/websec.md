# Web security testing

Test only authorized targets. Keep requests within the granted origin, identity, rate, and scope; obtain approval before expanding them.

```bash
h5i browser open https://target.example --capture
h5i websec requests --human
h5i websec show req_42 --raw
h5i websec replay req_42 --set query.id=456
h5i websec diff res_42 res_43 --human
h5i websec match res_43 --status 200 --contains ok
```

Use `h5i websec <command> --help` rather than guessing flags. Treat bodies and headers as sensitive. Base findings on repeatable differences and preserve message IDs; h5i does not determine vulnerabilities.
