###Use JavaScript to display your GitHub projects
####and host them for free on GitHub pages


Prerequisite: you should have multiple GitHub repositories already. If not, go back and create them.
If you have a linkedIn repository or blog or other sites you wish to link from this site then you can. If you have an existing domain (or want to register a new domain) then you can add links to that as well. Finally, I'll show you how to map your custom domain to the GitHub Pages site. 

GitHub Pages sites are publicly available on the internet. Even if their repositories are private. Sensitive data in your Page repository may be visible.

We will be creating this solution with GitHub, Prose, JavaScript, HTML, BootStrap, Gravatar, 

####Organize your existing GitHub repositories
This page will show repositories that have a description. So if you have a repository you don't want included then don't include a description. This page will display the repository name, the language and the description.

###Create a GitHub Pages repository
Head over to GitHub and create a new repository named username.github.io, where username is your username on GitHub.

If the first part of the repository doesn’t exactly match your username, it won’t work, so make sure to get it right. 

###Create a Readme.md file


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