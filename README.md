# Emotional Cities SDI template (Legacy)

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

[![DOI](https://zenodo.org/badge/413468166.svg)](https://zenodo.org/badge/latestdoi/413468166)