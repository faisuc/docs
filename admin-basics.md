# Vanilo Admin

> The Vanilo Admin package used to be the part of the vanilo/framework package in versions 0.x, 1.x and 2.x.  
> Beginning with v3.x, the Admin has been extracted from the Framework, and now it is optional.

The Admin Panel was built on top of the
[AppShell](https://github.com/artkonekt/appshell) library.

AppShell is being composed of the following parts:
- [User Module](users.md)
- [Acl Module](acl.md)
- [Customer Module](customers.md)
- [Menu Module](https://github.com/artkonekt/menu)
- [Address Module](addresses.md)

Vanilo adds the handling of products, categories and orders.

The Admin Panel has a Bootstrap 4 based UI. Probably it'll be themable
in the future if there'll be such demand.

The Admin's side menu was designed to be extensible, so it's possible to
add new menu items to it, or to alter existing ones.

## Changing Base URL Prefix

Admin URLs start with _'/admin/'_ by default. This can be changed in the
configuration:

```php
// config/concord.php
// Change both 'prefix' occurences
return [
    'modules' => [
        Konekt\AppShell\Providers\ModuleServiceProvider::class => [
            'routes' => [
                'prefix' => 'admin', 
            ],
        ],
        Vanilo\Admin\Providers\ModuleServiceProvider::class => [
            'routes' => [
                'prefix' => 'admin', 
            ],  
        ]
    ]
];
```
## Change Branding

You can change the App's name displayed on admin, the admin start URL
and the icon in top left.

```php
// config/concord.php
return [
    'modules' => [
        Konekt\AppShell\Providers\ModuleServiceProvider::class => [
            'ui' => [
                // Your app's name to display on admin
                'name' => 'Vanilo',
                // Admin Panel's base (eg. dashboard) URL
                'url'  => '/admin/product'
            ]
        ],
    ]
];
```

To set the admin's top left icon add the following file to your project:

`public/images/appshell/logo.svg`


