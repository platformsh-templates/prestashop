> [!WARNING]
> **This repository is no longer maintained by our internal teams.**  
> The template is provided *as is* and will not receive updates, bug fixes, or new features.  
> You are welcome to contribute on it or fork the repository and modify it for your own use.
> To deploy this template on [Upsun](https://www.upsun.com), you can use the command [upsun project:convert](https://docs.upsun.com/administration/cli/reference.html#projectconvert)
> on this codebase to convert the existing `.platform.app.yaml` configuration file to the [Upsun Flex format](https://docs.upsun.com/create-apps/app-reference/single-runtime-image.html).

# Prestashop for Platform.sh

This template builds Prestashop project.  It is pre-configured to use MariaDB.

PrestaShop is a freemium, open source e-commerce solution written in PHP.

## Features

* PHP 7.4
* MariaDB 10.4
* Composer-based build
* Automatic TLS certificates

## Customizations

The following changes have been made relative to Prestashop as it is downloaded from Prestashop.com. If using this project as a reference for your own existing project, replicate the changes below to your project.

* [.platform/routes.yaml](.platform/routes.yaml): Platform.sh allows you to define the [routes](https://docs.platform.sh/configuration/routes.html).
* [.platform/services.yaml](.platform/services.yaml):  Platform.sh allows you to completely define and configure the topology and [services you want to use on your project](https://docs.platform.sh/configuration/services.html).
* [.platform.app.yaml](.platform.app.yaml): You control your application and the way it will be built and deployed on Platform.sh [via a single configuration file](https://docs.platform.sh/configuration/app-containers.html).


## References

* [Platform.sh post](https://platform.sh/blog/2019/java-hello-world-at-platform.sh/)
* [Prestashop](https://www.prestashop.com/en)
* [PHP at Platform.sh](https://docs.platform.sh/languages/php.html)

## How to install

1. Clone this repository
2. Create a new platform.sh project

```
platform project:create
```

3. Add specific environment variables

```
platform -p<project> variable:set ADMIN_EMAIL your@email.com
platform -p<project> variable:set ADMIN_PASSWORD yourpassword
```

4. Push to platform.sh

```
git remote add platform <project id>@git.<project region>.platform.sh:<project id>.git
git push platform master
```

5. Backend

You can access your backend at `/admin-fwp` with the credentials that you defined as variables.
