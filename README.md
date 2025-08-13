Auto-deploy setup:
For this project, I've set it up so that commits pushed to main on Github will auto deploy the site files to my DigitalOcean droplet @:
https://johndecastro.site/

Setup:
1. Clone repo to local, edit, commit, and push to main
2. .github/workflows/deploy.yml triggers for every push to main
   Here, it checks out repo, starts SSH agent using private deploy key that is stored in Github secrets
   Adds droplet's host key to known_host
   Uses rsync to upload repo files to /var/www/johndecastro.site on droplet
3. Configured secrets where private key, server host, server user, and server paths are stored
4. Setup Droplet where dedicated SSH key was generated for actions and isntalled rsync on droplet.
5. Lastly, Github-Deploy,mp4 in repo showcases editing of file, commit and push to github, where actions run successfuly and updates site.
