# Security Notes for the Public Repository

This repository is intended for academic, lab, and portfolio use. FortiGate exports have been sanitized before publication.

Do not publish or commit:

- Administrator passwords
- HA authentication passwords
- IPsec pre-shared keys (PSKs)
- LDAP bind credentials
- Private keys
- Certificates containing private material
- API tokens or other service credentials

The configuration files in `configs/fortigate/` are reference copies with sensitive material removed. Recreated labs must supply their own secrets and environment-specific values.

If a real credential has ever been committed to a public Git history, treat it as exposed: rotate the credential first, then clean the relevant Git history where appropriate.
