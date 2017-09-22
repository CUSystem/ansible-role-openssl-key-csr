# Role Name

This is used for creating private keys and CSR for TLS certificate requests.

NOTE: This is just for RHEL, CentOS, EL. 

## Role Variables

Variables and defaults follow.

## Dependencies

No dependencies on other roles.

IMPORTANT: Using this role implies that you have accepted the Oracle license agreement to download the Oracle JDK and JCE. If you don't agree, don't use this role please.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- hosts: localhost
  vars:
    #Watch out because this is where your *PRIVATE* key will drop.
    build_dir:     /tmp

    country_name:             US
    state_or_province_name:   Colorado
    locality_name:            Denver
    organization_names:
      - Your cool org name
    organizational_unit_name: your unit name

    key_usage:
      - nonRepudiation
      - digitalSignature
      - keyEncipherment

    key_size:      4096
    subject_name:  server1.mydomain.local
    managing_team: my_team@email-place.com
    use_critical:  true
    alt_names:
      - server1.mydomain.local
      - www.mydomain.local
      - mail.mydomain.local
  roles:
  - staylorx.key-and-csr

## License

MIT

