# Emotional Cities SDI template (Raster)

This is a set of Docker images configured in a docker composition that contains:

- GeoServer
- Mapstore
- pygeoAPI
- PostGIS
- Apache web server
- OpenLDAP


## Random Notes

### Configuring GeoServer Authentication

Following this:

https://docs.geoserver.org/latest/en/user/security/tutorials/ldap/index.html#configure-the-ldap-authentication-provider

With this configuration:

**Server URL**: ldap://openldap:1389/dc=emotionalcities,dc=org
**User lookup pattern**: cn={0},ou=users

### SSL with Let's encrypt

If you are running Apache with SSL (recommended setup for production), create your SSL certificates first (for instance using [let's encrypt](https://letsencrypt.org/)) and edit this part of [httpd-ssl.conf](./apache-httpd/httpd-ssl.conf), to make sure it points to the right certificates:

```
    SSLCertificateFile    /etc/letsencrypt/live/oldskool.byteroad.net/cert.pem
    SSLCertificateKeyFile /etc/letsencrypt/live/oldskool.byteroad.net/privkey.pem
    SSLCertificateChainFile /etc/letsencrypt/live/oldskool.byteroad.net/fullchain.pem
```

Then, launch the stack using `docker-compose.yml`:

``` bash
docker-compose up -d
```
Or use the provided convenience script:

``` bash
./run_aws.sh
```

### To run on localhost

To run the composition on your localhost

``` bash
docker-compose -f docker-compose-local.yml up -d
```
