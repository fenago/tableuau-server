

tsm settings
============
You can use the `tsm settings` commands to export (get) and import (set)
configuration values.


-   [tsm settings
    export](https://help.tableau.com/current/server/en-us/cli_settings_tsm.htm#TSMExport)
-   [tsm settings
    import](https://help.tableau.com/current/server/en-us/cli_settings_tsm.htm#TSMSet)


**Important**: The server configuration file referenced in this topic
includes a copy of the master keystore file used for encrypting
configuration secrets. We strongly recommend that you take additional
measures to secure the node configuration file, using mechanisms as
described in [Securing secrets for import and export
operations](https://help.tableau.com/current/server/en-us/security_secret_storage.htm#Securing).

The following files are not exported or imported with this command. You
must manage these files manually:

-   SAML certificate file
-   SAML key file
-   SAML IdP metadata file
-   The custom certificate installed by [tsm security custom-cert
    add](https://help.tableau.com/current/server/en-us/cli_security_tsm.htm#custom-cert-add)
-   OpenID.static.file
-   Kerberos.keytab file
-   LDAP Kerberos keytab file
-   LDAP Kerberos conf file
-   Mutual SSL certificate file
-   Mutual SSL revocation file
-   Customization header logo file
-   Customization sign-in logo file
-   Customization compact logo file



##### tsm settings export
-----------------------------------------------------------------------------------------------------------------


Export the current server configuration and topology to a file.



#### Synopsis


`tsm settings export --output-config-file <path/to/output_file.json> [global options]`



#### Options


-f, \--output-config-file \<file\>

Required.

Specifies the location and name of the file created by this operation.



##### tsm settings import
--------------------------------------------------------------------------------------------------------------


Import server configuration or topology.



#### Synopsis


`tsm settings import --import-config-file <path/to/import_file.json> [global options]`



#### Options


-f,\--import-config-file \<FILE\>

Required.

Path to input file.

\--config-only

Optional.

\--topology-only

Optional.

-frc, \--force-keys

Optional.

Force a key to be added to configuration even if it did not previously
exist.



##### Global options
----------------------------------------------------------------------------------------------


-h, \--help

Optional.

Show the command help.

-p, \--password \<password\>

Required, along with `-u` or `--username` if no session is active.

Specify the password for the user specified in `-u` or `--username`.

If the password includes spaces or special characters, enclose it in
quotes:

`--password "my password"`

-s, \--server https://\<hostname\>:8850

Optional.

Use the specified address for Tableau Services Manager. The URL must
start with `https`, include port 8850, and use the server name not the
IP address. For example `https://<tsm_hostname>:8850`. If no server is
specified, `https://<localhost | dnsname>:8850` is assumed.

\--trust-admin-controller-cert

Optional.

Use this flag to trust the self-signed certificate on the
TSM controller. For more information about certificate trust and
CLI connections, see [Connecting
TSM clients](https://help.tableau.com/current/server/en-us/tsm_overview.htm#Connecti).

-u, \--username \<user\>

Required if no session is active, along with `-p` or `--password`.

Specify a user account. If you do not include this option, the command
is run using credentials you signed in with.
