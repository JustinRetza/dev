## Hydro's Dev Repo
#### Craft Development Testing

********************

##Directory Structure:

- `/bower_components` - where bower gets installed when running `$bower install`
    - `/foundation-sites`
    - `/jquery`
    - `/motion-ui`
    - `/what-input`
- `/craft/` - where you put your [craftcms](http://craftcms.com/) installation (step 2 above)   
- `/node_modules/` - where node gets installed when running `$npm install`
- `/site/` - where you point apache
    - `/lib` - compiled when you run `foundation watch` or `foundation build`
        - `/css`
            - `/display.css` - the single css generated by gulpfile.babel.js (line 63)
        - `/gr` - fonts moved from /src/ by gulpfile.babel.js (line 42)            
        - `/gr` - your compressed graphics generated by gulpfile.babel.js (line 90)
        - `/js`
            - `/app.js` - the single js generated by gulpfile.babel.js (line 78)            
        - `/svg` - svg moved from /src/ by gulpfile.babel.js (line 42)                 
- `/src`
    - `/fonts` - source fonts here
    - `/gr` - put your source graphics here and auto-compress them on build
    - `/js`
        - `/app.js` - adds $(document).foundation(); at the end of your compiled js
    - `/scss` - source foundation 6 sass files
        - `/components` - your custom sass/css goes inside here
        - `/mixins` - your custom mixins go inside here
        - `/_settings.scss` - a copy of the default Foundation config
        - `/app.scss` - included foundation dependencies
    - `/svg` - source svg files
- `/bower.json` - module configuration for your `/bower_components/`
- `/config.yml` - central config file to manage your paths and foundation components
- `/gulpfile.babel.js` - where it all comes together - update according to your needs
- `/package.json` - module configuration for your `/node_modules/`
- `/README.md` - this file =)

********************

## Other notes:

#### Keeping your npm up-to-date

update npm globally:

    $ sudo npm install npm@latest -g

#### Updating your project /node_modules/ (npm dependencies)

see what's outdated within `/your_project_dir/`:

    $ npm outdated -g --depth=0

update npm packages within your_project_dir and record the new version references in your `package.json`:

    $ npm update --save

#### Updating your project /bower_components/ (your main source for Foundation 6.2-> etc)

update bower globally:

    $ sudo npm install -g bower-update-all

update `/bower_components/` within `/your_project_dir/`:

    $ bower-update-all
