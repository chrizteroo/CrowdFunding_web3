**Crowdfunding web3 Development**

Folder structure full stack web3 application
Create an empty folder name it crowdfunding
Drag and drop into vscode
NOTE: there will be 2 sides for our application 1 is the client side where our yarn code will reside,
 first create a folder name
 it client inside the crowdfunding environment
 to initialize, open terminal

npx thirdweb@latest create contract 
Ok to proceed? Y
choose name for your project example web3
press enter to choose Hardhat
choose the name of smart contract example Crowdfunding
choose empty contract
cd web3
install enviroment varaible to make our development secure
npm install dotenv
Go to contract.sol
rename it to CrowdFunding.sol
also rename MyContract to CrowdFunding
 configure CrowdFunding contracts
Next go to Hardhat config.js

NOTE: we need to download metamask wallet.
please google how to download metamask
store your private key in side the environment variable
web3 folder create a new .env and paste your metamask private key
PRIVATE_KEY=7344659946655656462564666266562265565644765........
check .gitignore to make sure .env is added there.
Now we can use our private key to connect to Goerli network
Next google Goerli RPC to be able to get EndPoint Ethereum which we are connecting to for our test.

ankr.com/rpc/eth/eth_goerli/

back to hardhatconfig.js
set default network to 'goerli',
networks:{
hardhat:{},
 goerli:{
url: 'https://rpc.ankr.com/eth_goerli' ,
accounts: [`0x${process.env.PRIVATE_KEY}`]
}
},
}
}
};

Go to package.json adjust a single command "deploy"
NOTE: You do not need to configure the private key,if you want to use web3file, just use npx thirdweb deploy, your work will be deployed to thirdweb easily.
go to terminal make sure you are in web3 folder
npm run deploy
NOTE: it will run the deploy instance and create artifiacts
npm run deploy
thirdweb page should open
connect metamask wallet from drop menu
connect with Metamask  page select account and   click next 
click connect
checcj I have read and agree window button and click continue
click confirm
click confrim the second time
 now our contract is deployed
Now our contract is deployed.
build, and deploy contract on thirdweb.

Now we build the front end interface using react framework
Go back to terminal
and cd to the root folder

cd to the client repository
npx thirdweb create --app
enter
insert OK to proceed? y
enter
what is your project named?
type in ./
which blockchain do you want to use?
select EVM 
press enter
what framework do you want to use?
select Vite
press enter
What langauge do you want to use?
select JavaScript
press enter
NOTE: That is all our application has been initialized 
now go to client folder to see what was downloaded.
Go to package.json
check all the downloads make sure we have react-dom
if its not there, go back to terminal and install
npm install react-router-dom
NOTE: Just download it since we only have react-dom not react-router-dom

once it is downloaded run 
npm run dev
click on the localhost:5173/
welcome to thirdweb! should appear
close the welcom browser
on the terminal use control C to stop the appication

Next Delete the entire source SRC folder
then go to Client repository and create a new folder from scratch called src 
there, create new file, index.js
NOTE: This will be the starting point of every single react application
inside the file, import react,react-dom/client,react-router-dom
also import BrowserRouter as Router from react-router-dom
and finally import ChainId, ThirdwebProvider 
NOTE: see reference code for more inputs
Next 
Still inside the source create  another file App.jsx
 inside App.jsx just run rafce for now, will add components later
NOTE: rafce is a snippets comming from ES7 React/Redux/React-Native
if you dont have it you may download it on vscode
Naviagte back to main.jsx and add import App 
NOTE: I created it as Main.js and App.js 
changed it to jsx once I downloaded react

install tailwind go to tailwindcss.com/docs/guide/vite

npm install -D tailwindcss postcss autoprefixer
after download init
npx  tailwindcss init -p
Note: this will create tailcss config file
open tailwind.config.js file
add the content:
"./index.html"
"./src/**/*.{js,ts,jsx,tsx}"
next,
create a new file index.css inside the src folder 
add the tailwind directives to your css
paste the directive there.
NOTE: you may also add css of your choice for fonts

create in src assets folder
add all assets you need to beautify the page
NOTE: download assets from file provided
inside the assets folder create index.js file and import all assets to be used and export same.

create a new folder in src called constants, inside crea a file called index.js
in it we have the navlink, and all other page navigation. check the code in my github

create another folder in src called context. This one is very important, since it is where we going to create react context API, it is the heart of the whole development operation.

 next create also in src, components folder, pages folder, and utils folder.
Inside of the utility functions(utils) create a file index.js
Check Github for other files created
NOTE: everything is starting from App.jsx 
Go to App.jsx and configure
 Important NOTE:
Encountered vite unexpected token error comming from my index.css, it was a vite build error.
After some investigation, I discovered it was my node.
Luckily I was using NVM I then checked the version I had, it was 19^
I now use nvm install 18.12.1
This was the LTS 
After this, 
I ran npm update.
The following occured:
1. The problems tab has no problem listed
2. th npm updated was succesfull with added 2 packages, removed 1 package, 
changed 2 packages, and audited 770 packages in all, found 0 vulnerability.
I now run npm run dev It was working as expected. 

Navigate back to App.jsx 
import Sidebar Navbar, from components, and also import the Home, CampaingDetials etc from pages
 Go to side bar and create components
check in the front end if it works
go to Navabar and create components, do same for all other components, inside pages, import them in App.jsx in order to view it on the default page.

NOTE: Getting Unknown at rule @tailwind css (unknownAtRules)
in my case it was
@tailwind base;
@tailwind components;
@tailwind utilities;
The 3 in my style.css file

The following are the steps to fix it
in vscode open settings
search for "unknown" the first result should be the on you are looking for.
css > Lint : Unknown at Rules
Make sure you are under user, and change 
CSS> Lint:Unknown at Rules
Unknown at-rule.
Change the drop menu to ignore
save.
Check again on Style.css
it should be working.
