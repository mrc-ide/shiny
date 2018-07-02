## mrc-ide shiny

Address https://shiny.dide.ic.ac.uk

### Administration

Adding new users or set up aliases to particular apps

1. Edit `/etc/shiny-server/shiny-server.conf`
2. Restart the shiny server `sudo systemctl restart shiny-server`

If it's a new user add them to the shiny group with `usermod -a -G shiny <username>`

Whitelist apps

1. Edit `/etc/apache2/sites-available/000-default.conf` to add a block

```xml
   <Location /whitelistedlocation>
    Satisfy Any
    Allow from all
   </Location>
```
2. Reload (not a restart) apache with `sudo /etc/init.d/apache2 reload`
