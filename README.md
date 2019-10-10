# markpedia

Wikipedia in Markdown format:

1. clone the project [github.com/rognoni/markpedia](https://github.com/rognoni/markpedia)
1. create a new MediaWiki markup file, for example [wiki/Anti-pattern.wiki](https://en.wikipedia.org/w/index.php?title=Anti-pattern&action=edit)
1. execute the command `pandoc -s Anti-pattern.wiki -o Anti-pattern.md`
1. edit style and content, for example add `.md` extension to the wiki-links
1. update [data/redirects.json](data/redirects.json) and FIX the wiki-links
1. push and browse [https://raw.githubusercontent.com/rognoni/markpedia/master/wiki/Anti-pattern.md](https://monastic.netlify.com/#/url/https://raw.githubusercontent.com/rognoni/markpedia/master/wiki/Anti-pattern.md)
1. make a pull request
