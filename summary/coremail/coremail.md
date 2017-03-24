## Coremail	[Back](./../summary.md)

This note is mainly used to remember some developming details and working details in the Coremail inc..

### Domains

Firstly, there is a list of sites for remember:

- OA: http://oa.mailtech.cn/ (OA system for original works)
- Lunkr: http://www.lunkr.cn/ (used for internal communications)
- GitLab: http://git.mailtech.cn/ (used for storing projects)
- Developing Center: http://rd.mailtech.cn/ (used for checking some documents and depoying status)
- Wiki: http://wiki.mailtech.cn/ (detailed information about any transactions in the company)
- Email System: http://mt.icoremail.net/ (for receiving and sending emails)

### Development

Then, how to develop?

#### Local installation

The main projects is `cmj`, and install it locally according to [the document](http://git.mailtech.cn/coremail/cmj).

As you can see, it's a Java project, and it means that you may have to use a Java IDE to develop, among which **IDEA** is the choice of this company.

To setup configurations for the Tomcat server, you can run the script:

```bash
node {project_root}/dev/setup.js
```

Then, specify where the Tomcat has been installed according some official documents.

When it comes to the structure of this project, there are three sub-projects:

- **javalib2**
- **templage.NG**
- **wmsvr**

As a front-end developer, what I should focus on is the project **template.NG**, which mainly used to develop templates of Coremail system. In the folder `web`, there are different kinds of templates developed before like `coremail.pad`, `coremail.XT` series, etc. And in the folder `web.modules`, you can see that `coremail.XT5` is under development.

When developing XT5, it's recommended to read documents firstly:

- As it uses webpack v1.x to build dependencies, ES6 is not supported at all
- When developing JavaScript or HTML, use `gulp watch:dev:js` to watch building process
- When developing Less, use `gulp watch:dev:css` to watch building process