# Wiki|Docs
Just a databaseless markdown flat-file wiki engine.

Project homepage: [https://www.wikidocs.it](https://www.wikidocs.it)

*Please consider supporting this project by making a donation via [PayPal](https://www.paypal.me/zavy86)*

[![Wiki|Docs presentation and contributors recruitment on YouTube](https://wikidocs.it/documents/homepage/cover-side-project-wikidocs-youtube.jpg)](https://www.youtube.com/watch?v=NFILGeozt7k "Watch Wiki|Docs presentation and contributors recruitment on YouTube")

## Features
- Open source
- Plain text files
- No database required
- Markdown syntax
- Editor full WYSIWYG
- Unlimited page revisions
- Uploading images (also from clipboard)
- Content can be categorized in namespaces
- Automatic generated index and sitemap
- Public and private browsing
- Syntax highlighting
- Dark mode
- and many more..

## Demo
Try the demo playground at: [http://demo.wikidocs.it](http://demo.wikidocs.it)

Authentication code is: `demo`

## Setup
### Manual
- [Download](https://github.com/Zavy86/wikidocs/releases) the lastest release
- Clone the repo `git clone https://github.com/Zavy86/wikidocs.git`

### Docker
There is a [Docker image](https://hub.docker.com/r/reyemxela/wikidocs) that sets up WikiDocs with Apache2 and PHP automatically.
#### Quick run
```
docker run -d -p 80:80 -v /path/to/documents:/documents -e PUID=1000 -e PGID=1000 reyemxela/wikidocs
```
#### docker-compose
```
version: '2'

services:
  wikidocs:
    image: reyemxela/wikidocs
    environment:
      - PUID=1000
      - PGID=1000
    ports:
      - 80:80
    volumes:
      - /path/to/documents:/documents
```

## Configuration

### Automatic
- The `setup.php` script will automatically create both `config.inc.php` and `.htacess` files

### Manual
- Copy the configuration sample file `cp config.sample.inc.php config.inc.php`
- Edit the configuration file `nano config.inc.php`
- Create the `.htaccess` file like:
```
<IfModule mod_rewrite.c>
	RewriteEngine On
	RewriteBase /wikidocs/
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteRule ^(.*)$ index.php?doc=$1 [NC,L,QSA]
</IfModule>
```
- Make sure that RewriteBase is the same as the PATH in the configuration file

## Developers

### Creator
**Manuel Zavatta**
- [GitHub](https://github.com/Zavy86)
- [WebSite](http://www.zavy.im)
- [Contacts](mailto://manuel.zavatta@gmail.com)

### Contributors
- [**Alex Meyer**](https://github.com/reyemxela)
- [**Bo Allen**](https://github.com/bitwisecreative)
- [**Micha**](https://github.com/serial)

## License
Code released under the MIT License
