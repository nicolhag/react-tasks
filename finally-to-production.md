---
description: 'This assignment is highly optional, but very rewarding and fun(c) to do.'
---

# Finally, off to production! 🚀

## Make a public React app! {#gjør-nettsiden-din-offentlig}

For now, we have worked in CodeSandbox. But, wouldn't it be great fun to make it public? Nothing like showing off to your family and friends!

### Add version control {#sett-opp-versjonskontroll-på-koden}

[Git](https://git-scm.com/) is todays standard for version control. Version control is not only good for finding back to the ancient times of code, but is also actively used when developing in team. 

Head over to Facebook's Github-page for setting up your own repo with: [Create React App](https://github.com/facebook/create-react-app). We find this pretty straight-forward to use if you just follow the instructions :\) 

### Publish your repo at Heroku {#publiser-koden-på-heroku}

Create a user at [Heroku](https://heroku.com/). Heroku is a easy-to-use cloud service, letting you publish your code automatically through automatic integration with Github. 

> There are many other cloud services like Heroku out there; the most notable ones being AWS, Google Cloud og Azure. When it comes to small spare-time projects, Heroku and [Firebase](https://firebase.google.com/) are two good and easy-to-use services. 
>
> **Beware!** Some of the services offered by these sites, including Firebase, are paid services. Most of the time, this is not necessary at all.

**1. Create a new Heroku app**

In the right corner at Heroku, click the "New" button, and choose "Create new app". Choose a vacant site name.

**2. Connect you app to Heroku**

Go to the "Deploy" tab at the Heroku website, if you're not there already. As you can see, there a multiple ways to setup the deployment. Choose the Github integration and follow the instructions. Heroku will need access to the repositories connected to your Github account - if you feel uncomfortable with this, don't do it :\) 

Inside Heroku, we recommend using Automatic Deploys. This way, your site will always be updated at your Heroku app updates every time new code finds its way to the `master`-branch.

If you encounter the following error message while deploying: 

```text
! No default language could be detected for this app.
HINT: This occurs when Heroku cannot detect the buildpack to use for this application automatically.
See https://devcenter.heroku.com/articles/buildpacks
! Push failed
```

...please add `Node` as buildpack under the app settings, and you _should_ be ready to go!

Really, there's not much more to it than that. Congratulations, you have set your app into production with automatic deploys! 🎉

**Bonus: setup a custom domain**

If you own a domain, you can click your way into the Settings tab inside Heroku and add a custom domain. You will also need to setup a pointer back to your Heroku instance at your DNS provider. Typically, you set `CNAME` or `ALIAS`For this part, Heroku supplies a pretty good guide here on how to connect your app to your own domain: [https://devcenter.heroku.com/](https://devcenter.heroku.com/).

