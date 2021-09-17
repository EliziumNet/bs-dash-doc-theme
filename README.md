# Bootstrap Dash UI Github Pages Documentation Template

This is a designed to become a Gh Pages template used for documenting Elizium projects. The idea behind this is to be able to create a visually appealling documentaion template. The alternatives to this approach are to use other platforms such as [docusaurus](https://docusaurus.io/) or [gitbook](https://www.gitbook.com/). Whilst these are both great platforms, gitbook, has its own rather severe limitations and docusaurus has its own fixed appearance which although perfectly fine, is not as visually appealling as other bootstrap themes.

What I want to do is to be able to use any 3rd party bootstrap theme and combine that with the Jekyll platform. This serves as a bootstrap learning opportunity to build a static web site for documentation purposes.

Some bootstrap themes such as the excellent [Dash UI](https://codescandy.com/dashui) use gulp as the build tool and can be intergerated with with jekyll with the npm module [gulp-gh-pages](https://www.npmjs.com/package/gulp-gh-pages). The only major addition I would like to make to Dash UI would be to add a right hand side sidebar as illustrated in the [Bootstrap cheatsheet example](https://getbootstrap.com/docs/5.1/examples/cheatsheet/). However, doing so introduces a slight change in the way the static website is built. Usually, one would enable gh-pages on the repo and then select a theme from the gallery. In this setup, the user would setup this build chain by creating a config.yaml. The jekyll infrasture on gh-pages would use this to perform its build. However, with the use of gulp-gh-pages, we can turn this on its head, by performing the build locally and then publishing the site directly to gh-pages (see [Using Gulp with Jekyll](https://aaronlasseigne.com/2016/02/03/using-gulp-with-jekyll/)), by-passing jekyll on the server. As this is the static website, the built site contents (typically created in a dist or \_site directory) can also be committed into source control as well as the source.

This is a rarely used setup, but I am using this for the following reasons:

1) I want to learn bootstrap, without getting bogged down with also learning a js framework at the same time (that'll come later)

2) I want to be able to use any 3rd party bootstrap theme. I could write the bootstrap from scratch, but my current skill level prevents me from doing so. I don't want to start with a blank sheet of paper; Dash UI is pefect for my documentation needs.

3) Don't want to be restricted to writing just markdown files, becasue that significantly reducing presentation options and wouldn't allow for learning bootstrap.

4) Since this is a template repo, I want to be able to define static data in client documentation repos for the specific content and then define the template with generic content with front matter and liquid which can easily be inherited.

5) Pusblishing a pre-built site to gh-pages proves that we can use any tool chain we want to build the website on a client machine and publish the result artefacts to gh-pages, bypassing Jekyll on the server side. This also means that unit tests can be run as part of the build process; I'm not sure how you could do this when using jekyll on the server (gh-pages).

6) Reusing this template in client repos is easy (see [Jekyll Themes](https://jekyllrb.com/docs/themes/)), just specify remote_theme inside the \_config.yaml:

> remote_theme: EliziumNet.bs-dash-ghp-doc-template

As time goes by, enhancements can be made to the template which are immediatley inherited by the clients. This is in contrast to the github template paradigm, where a repo can be marked as a template and then users can take a one time snapshot of the template. If changes occur to the template, these enhancements are not immediately inherited, the client would have to be manually updated to aquire those changes.

:Warning: My assumption about being able to resue an existing theme, may not be quite what I think it is. I may need to create a gem-based theme using the Jekyll __new-theme__ command; time will tell. But I think this is only required if you want to publish your theme to a repository like jekyllthemes.org.
