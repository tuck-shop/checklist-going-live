> Our checklist for all projects that are going live
> Forked from Spatie.

## 1. Browserstack tests
- [ ] Desktop: test on latest versions of Chrome, IE/Edge, Firefox, Safari
- [ ] Mobile: test on latest versions of Mobile Safari, Android

## 2. Front end checklist

### Assets
- [ ] Webfonts: is the live domain configured in services like Typekit, Fonts.com etc.?

### Scripts
- [ ] Check for console errors

### Page weight
- [ ] Check if heavy assets are cached

### Audits
- [ ] Use the Chrome DevTools (in incognito mode) and perform a mobile audit (with throttling) to fix common problems.
- [ ] Repeat with a desktop audit.

## 3. Check content (with an open console)
- [ ] Does menu/submenu have a correct active state on every page?
- [ ] Are 404, 500 and 503 pages provided? Do they provide useful content like 'back to home', search or a navigation tree?

### Meta
- [ ] Check page titles / descriptions
- [ ] Test Facebook sharing.
- [ ] Does Favicon load?

### Components
- [ ] Google Maps
    - [ ] API key needed/configured?
    - [ ] Check info windows
    - [ ] Prevent zoom out beyond 1x world
    - [ ] Try clicking on markers
- [ ] Forms: fill out with wrong/right values
- [ ] Video: check with sound on
- [ ] Try subscribing to a newsletter with incorrect & correct email (use correct mail twice to get 'already subscribed' message)
- [ ] Check structured data for news, events, products,... https://search.google.com/structured-data/testing-tool/

## 4. Back end checklist
- [ ] Check for all user permissions in Craft CMS
- [ ] Check for any unused plugins
- [ ] Ask someone to sanity check all .env values
- [ ] Check any .htaccess files aren't ruining the world
- [ ] Check the assets are coming from the correct AWS Bucket
- [ ] Check sitemaps aren't being generated for entries we dont want


## 5. Server, DNS & Services
- [ ] Add redirects from old to new pages if necessary.
- [ ] Install Let's Encrypt certificate
- [ ] Check your hostfile to make sure you're looking at the live site
- [ ] Test all www and non www domains and http and https redirects are working - use the `checkredirects domain.com` command
- [ ] Verify that indexing is not prohibited with `x-robots-tag: none` by checking `curl -I https://url | grep 'x-robots-tag'`. Allow robots in `.env`
- [ ] Check dns propagation with https://www.whatsmydns.net/
- [ ] Verify Tag Manager / Analytics have been correctly set up
- [ ] Set up email routing at cloud above (if using) and test

### Google Search Console
- [ ] Submit all www/non-www http/https variations
- [ ] Crawl > Fetch as Google > Submit to index to kickstart index

### Server
- [ ] Are relavent backups enabled?
- [ ] Is artisan scheduled on Forge (only applied to Laravel sites)?
- [ ] Is Horizon configured in Supervisor on Forge? Command should be `php artisan horizon`. Path should be `/home/forge/my-new-site.com/current`
- [ ] Is the url being monitored by uptime robot?
- [ ] Is the site being monitored by Ghost Inspector?

### Github
- [ ] Check the branch restrictions are in place

