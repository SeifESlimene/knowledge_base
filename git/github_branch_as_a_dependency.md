How and why to use a Github branch as a dependency in your package.json
The combination of Open Source and GitHub is amazing. I can not count the times a freely accessible library or tool saved me countless hours or allowed me to built something I wasn’t otherwise capable of.

But sometimes you might not be happy with how a library/framework/tool/whatever handles something and you need a little change. Oftentimes for me that requirement is so specific to my project or problem that creating an issue makes no sense. Or maybe there is just no time to wait on a response and update.

Luckily you can fork a GitHub repository, change or fix it yourself and then pull the repo into your project right from there instead of pulling the npm package in. You can even point to a specific branch.

You can do this by either running the npm or yarn command on the CLI or by going the manual way editing the package.json

Command line
npm install --save-dev username/repo#branch-name
yarn add --dev username/repo#branch-name
Manual way
Open package.json, to to the "devDependencies" or "dependencies" key and add your package in the following format:

"package-name": "username/repo#branch-name",
And then install the package with npm install or yarn.

Don’t forget
If you already had the original version of the package in your project, make sure to remove it (and install your new package).

rm -rf ./node_modules/package-name && npm install
rm -rf ./node_modules/package-name && yarn
Or find the folder inside node_modules you want to replace and remove it and then npm install or yarn again.

If the change/update might be of interest for others too you can also create a Pull Request to the original package and see if your changes make it into the Repository and then you can maybe switch back to the original later.

This has the advantage that you will get further updates - which you won’t get in your own forked version. But Depending on your changes or needs that might also be a good thing. As always: It depends.
