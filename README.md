#digital_ocean_haskell
## 

digtal_ocean_haskell is a haskell library that provide easy access to digitalocean.com APIs to manage droplets, images and more.

## How to install

You can install python-digitalocean using **pip**

    cabal install digital-ocean

## Features
digital_ocean_haskell support all the features provided via digitalocean.com APIs, such as:

* Get user's Droplets
* Get user's Images (Snapshot and Backups)
* Get public Images
* Get Droplet's event status
* Create and Remove a Droplet
* Resize a Droplet
* Shutdown, restart and boot a Droplet
* Power off, power on and "power cycle" a Droplet
* Perform Snapshot
* Enable/Disable automatic Backups
* Restore root password of a Droplet


## Examples
### Shutdown all droplets

This example shows how to shutdown all the active droplets:

```haskell
import DigitalOcean
manager = Manager token="secretspecialuniquesnowflake"
my_droplets = get_all_droplets manager
map shutdown my_droplets
```

### Creating a Droplet and checking its status

This example shows how to create a droplet and how to check its status

```haskell
import DigitalOcean
droplet = Droplet{token="secretspecialuniquesnowflake",
                               name='Example',
                               region='nyc2', -- New York 2
                               image='ubuntu-14-04-x64', -- Ubuntu 14.04 x64
                               sizeSlug='512mb',  -- 512MB
                               backups=True}
createDroplet manager droplet
```

### Checking the status of the droplet
```haskell
actions = getActions droplet manager
map load actions
```

## Links

  * Project Site: [http://arnoblalam.github.io/haskell_digital_ocean](http://arnoblalam.github.io/haskell_digital_ocean)
  * GitHub: [https://github.com/arnoblalam/digital_ocean_haskell](https://github.com/koalalorenzo/python-digitalocean)
  * Author Website: [http://arnoblalam.github.io](http://arnoblalam.github.io)
