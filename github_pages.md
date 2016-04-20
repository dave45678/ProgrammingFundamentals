###Use JavaScript to display your GitHub projects
####and host them for free on GitHub pages


**Prerequisite**: you should have multiple GitHub repositories already. If not, go back and create some. If you use linkedIn or have a blog you wish to link from this site then you can. I'll also show you how to redirect a custom domain to this site as well. You can use your existing domain or register a new domain. 

GitHub Pages is a free offering from GitHub.com. Pages allows you to host pages. The pages can be for a particular project. Or they can be for something else. Today we're going to look at something else - a resume. GitHub Pages sites are publicly available on the internet. 

**Technologies**: We will be creating this solution with GitHub, Prose, JavaScript, HTML, BootStrap, Gravatar. You will not need to install anything on your computer. Everything we use in this tutorial is free. You can also register a domain with  hover.com or another provider. Registering the domain is not free. You do not need to register a domain for this tutorial.  

####Organize your existing GitHub repositories
This page will list repositories that have a description. If you have a repository you don't want included then don't fill in the description. This page will display the repository name, the programming language and the description.

###Create a GitHub Pages repository
Create a new GitHub repository named username.github.io, where username is your username on GitHub.  The first part of the repository must exactly match your username. 

###Create a Readme.md file
It's just good practice to have a Readme file for every project. The Readme file  is a good place for a brief summary of your project.

###Working from the GitHub site
You can complete this tutorial without additional software if you wish to work directly in the browser. Browse to Prose.io and allow Prose to access your GitHub repositories. Then select the GitHub Pages repository you created above.

###Working from your computer
If you wish to complete this tutorial from your computer then you need to clone your repository. Open a terminal in your home or workspace folder. 
```
git clone https://username@github.com/username/repositoryname.git
```

**List git commands you need**

###Create an index page 
Create a web page called index.html.  A minimal HTML5 page is below. You can create this page locally or work directly from GitHub. 
```html
 <!DOCTYPE html>
<html>
<head>
<title>Your Page Title</title>
</head>
<script>
</script>
<body>

</body>
</html> 
```

###Add a link to include jQuery
jQuery is a JavaScript library which simplifies HTML scripting. It's free and open-source. We'll use jQuery to get the repository list. The script below will parse through the JSON-formatted list. It will generate an HTML list of your GitHub projects with descriptions.

Add the script tags for the JQuery library just below the closing head tag. Do not put these in between the other script tags. You'll use them in the next step. 
```html
<!-- jQuery library -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.0/jquery.min.js"></script>
```

Add the following code between script tags or as an external script. I saved mine in a file called listrepos.js which is in the javascript directory.


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
I saved my scripts in a file called listrepos.js. It's in the scripts directory I created. I then added the code below to the index.html page. It should appear just before the closing tag for ```</head>```.


```html
<script src="scripts/listrepos.js"></script>
<script>
    $(function() {
        $("#my-github-projects").loadRepositories("dave45678");
    });
</script>
```
Your index page should now showyour repositories.

###Add a Gravatar


###Add Bootstrap

###Add a link to LinkedIn (or your blog, etc)


###Check out your page


###Register a domain
hover.com

###Add a CNAME file

###
https://api.github.com/users/dave45678/repos