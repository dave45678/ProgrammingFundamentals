###Use JavaScript to display your GitHub projects
####and host them for free on GitHub pages

Create a web page called index.html



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
