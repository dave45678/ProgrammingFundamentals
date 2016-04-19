###Use JavaScript to display your GitHub projects
####and host them for free on GitHub pages


**Prerequisite**: you should have multiple GitHub repositories already. If not, go back and create them. If you use linkedIn or have a blog you wish to link from this site then you can. I'll also show you how to redirect a custom domain to this site as well. You can use your existing domain or register a new domain. 

GitHub Pages is a free offering from GitHub.com that allows you to sites are publicly available on the internet. 

**Technologies**: We will be creating this solution with GitHub, Prose, JavaScript, HTML, BootStrap, Gravatar. All those are free. We will register a domain with  hover.com. Registering the domain is not free. You do not need to register a domain for this tutorial.  

####Organize your existing GitHub repositories
This page will show repositories that have a description. So if you have a repository you don't want included then don't include a description. This page will display the repository name, the programming language and the description.

###Create a GitHub Pages repository
Create a new GitHub repository named username.github.io, where username is your username on GitHub. GitHub documentation says that the first part of the repository must exactly match your username. 

###Create a Readme.md file
It's just good practice to have a Readme file for every project. The Readme file  is a good place for a brief summary of your project.

###Create an index page 
Create a web page called index.html.  A minimal HTML5 page is below.
```html
 <!DOCTYPE html>
<html>
<head>
<title>Your Page Title</title>
</head>
<body>

</body>
</html> 
```



1. Add the following code between script tags or as an external script. I saved mine in a file called listrepos.js which is in the javascript directory.


```javascript
jQuery.githubUser = function(username, callback) {
   jQuery.getJSON('https://api.github.com/users/'+username+'/repos?callback=?',callback)
}
 
//this method
jQuery.fn.loadRepositories = function(username) {
    this.html("<span>Querying GitHub for " + username +"'s repositories...</span>");
     
    var target = this;
    $.githubUser(username, function(data) {
        var repos = data.data; // JSON Parsing
        sortByName(repos);    
     
        var list = $('<dl/>');
        target.empty().append(list);
        $(repos).each(function() {
        	if ((this.description).length>0){
	            if (this.name != (username.toLowerCase()+'.github.com')) {
	                list.append('<dt><a href="'+ (this.homepage?this.homepage:this.html_url) +'">' + this.name + '</a> <em>'+(this.language?('('+this.language+')'):'')+'</em></dt>');
	                list.append('<dd>' + this.description +'</dd>');
	            }
        	}
        });      
      });
      
    function sortByName(repos) {
        repos.sort(function(a,b) {
        return a.name - b.name;
       });
    }
};

```
2. Add the following code to the index.html page. It should appear just before the closing tag for ```</head>```.


```html
<script src="scripts/listrepos.js" type="text/javascript"></script>
<script type="text/javascript">
    $(function() {
        $("#my-github-projects").loadRepositories("dave45678");
    });
</script>
```


https://api.github.com/users/dave45678/repos