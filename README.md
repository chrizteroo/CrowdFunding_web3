**Crowdfunding web3 Development**

**Folder structure full stack web3 application**
1. Create an empty folder name it crowdfunding
2. Drag and drop into vscode
>NOTE: there will be 2 sides for our application 1 is the client side where our yarn code will reside,
 3. first create a folder 
 4. name it client inside the crowdfunding environmentto initialize, 
 5. open terminal

6. npx thirdweb@latest create contract 
7. Ok to proceed? Y
8. choose name for your project example web3
9. press enter to choose Hardhat
10. choose the name of smart contract example Crowdfunding
11. choose empty contract
12. cd web3
14. install enviroment varaible to make our development secure
15. npm install dotenv
16. Go to contract.sol
17. rename it to CrowdFunding.sol
18. also rename MyContract to CrowdFunding
 **configure CrowdFunding contracts**
19. Next go to Hardhat config.js

>NOTE: we need to download metamask wallet.
20. please google how to download metamask
21. store your private key in side the environment variable
22. web3 folder create a new .env and paste your metamask private key
>PRIVATE_KEY=7344659946655656462564666266562265565644765........
23. check .gitignore to make sure .env is added there.
>Now we can use our private key to connect to Goerli network
24. Nextgo to google Goerli RPC to be able to get EndPoint Ethereum which we are connecting to for our test.

>ankr.com/rpc/eth/eth_goerli/

25. back to hardhatconfig.js
26. set default network to 'goerli',
>networks:{
>hardhat:{},
 >goerli:{
>url: 'https://rpc.ankr.com/eth_goerli' ,
>accounts: [`0x${process.env.PRIVATE_KEY}`]
}
},
}
}
};

27. Go to package.json adjust a single command "deploy"
>NOTE: You do not need to configure the private key,if you want to use web3file, just use npx thirdweb deploy, 
>your work will be deployed to thirdweb easily.
28. go to terminal make sure you are in web3 folder
29. npm run deploy
>NOTE: it will run the deploy instance and create artifiacts
30. npm run deploy
31. thirdweb page should open
32. connect metamask wallet from drop menu
33. connect with Metamask  page select account and   click next 
34. click connect
35. check, I have read and agree window button and click continue
36. click confirm
37. click confrim the second time

>Now our contract is deployed.
**Build, and deploy contract on thirdweb.**

>Now we build the front end interface using react framework
38. Go back to terminal
39. and cd to the root folder

40. cd to the client repository
41. npx thirdweb create --app
42. click enter
43. insert OK to proceed? y
44. enter
45. what is your project named?
46. type in ./
47. which blockchain do you want to use?
48. select EVM 
49. press enter
50. what framework do you want to use?
51. select Vite
52. press enter
53. What langauge do you want to use?
54. select JavaScript
55. press enter
>NOTE: That is all our application has been initialized 
56. now go to client folder to see what was downloaded.
57. Go to package.json
58. check all the downloads make sure we have react-dom
59. if its not there, go back to terminal and install
60. npm install react-router-dom
>NOTE: Just download it since we only have react-dom not react-router-dom
>once it is downloaded run 
61. npm run dev
62. click on the localhost:5173/
>welcome to thirdweb! should appear
63. close the welcom browser
64. on the terminal use control C to stop the appication

65. Next Delete the entire source SRC folder
66. then go to Client repository and create a new folder from scratch called src 
67. there, create new file, index.js
>NOTE: This will be the starting point of every single react application
68. inside the file, import react,react-dom/client,react-router-dom
69. also import BrowserRouter as Router from react-router-dom
70. and finally import ChainId, ThirdwebProvider 
>NOTE: see reference code for more inputs
>Next 
71. Still inside the source create  another file App.jsx
72. inside App.jsx just run rafce for now, will add components later
>NOTE: rafce is a snippets comming from ES7 React/Redux/React-Native
>if you dont have it you may download it on vscode
73. Naviagte back to main.jsx and add import App 
>NOTE: I created it as Main.js and App.js 
74. changed it to jsx once I downloaded react

75. install tailwind go to tailwindcss.com/docs/guide/vite

76. npm install -D tailwindcss postcss autoprefixer
77. after download init
78. npx  tailwindcss init -p
>Note: this will create tailcss config file
79. open tailwind.config.js file
>add the content:
"./index.html"
"./src/**/*.{js,ts,jsx,tsx}"
>next,
80. create a new file index.css inside the src folder 
>add the tailwind directives to your css
>paste the directive there.
>NOTE: you may also add css of your choice for fonts

81. create in src assets folder
82. add all assets you need to beautify the page
>NOTE: download assets from file provided
83. inside the assets folder create index.js file 
84. and import all assets to be used and export same.

85. create a new folder in src called constants, inside crea a file called index.js
86. in it we have the navlink, and all other page navigation. check the code in my github

87. create another folder in src called context. This one is very important, since it is where we going to create react context API, it is the heart of >the whole development operation.

 88. next create also in src, components folder, pages folder, and utils folder.
89. Inside of the utility functions(utils) create a file index.js
90. Check Github for other files created
>NOTE: everything is starting from App.jsx 
91. Go to App.jsx and configure
>Important NOTE:
>Encountered vite unexpected token error comming from my index.css, it was a vite build error.
>After some investigation, I discovered it was my node.
>Luckily I was using NVM I then checked the version I had, it was 19^
>I now use nvm install 18.12.1
>This was the LTS 
>After this, 
>I ran npm update.
>The following occured:
>1. The problems tab has no problem listed
>2. the npm updated was succesfull with added 2 packages, removed 1 package, 
>changed 2 packages, and audited 770 packages in all, found 0 vulnerability.
>I now run npm run dev It was working as expected. 

92. Navigate back to App.jsx 
93. import Sidebar Navbar, from components, 
94. and also import the Home, CampaingDetials etc from pages
95. Go to side bar and create components
96. check in the front end if it works
97. go to Navabar and create components, do same for all other components, 
98. inside pages, import them in App.jsx in order to view it on the default page.

>NOTE: Getting Unknown at rule @tailwind css (unknownAtRules)
>in my case it was
>@tailwind base;
>@tailwind components;
>@tailwind utilities;
>The 3 in my style.css file

>The following are the steps to fix it
>in vscode open settings
>search for "unknown" the first result should be the on you are looking for.
>css > Lint : Unknown at Rules
>Make sure you are under user, and change 
>CSS> Lint:Unknown at Rules
>Unknown at-rule.
>Change the drop menu to ignore
>save.
>Check again on Style.css
>it should be working.
