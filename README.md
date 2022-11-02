# Welcome to EdFRAX Projects

![](https://github.com/EdFRAX/NFT-Minting-Dapp-ERC-721A/blob/main/src/styles/logo-blob.png)

All the code in this repo was created, explained by [HashLips](https://github.com/HashLips) and this dapp is designed by [EdFRAX](https://www.youtube.com/EdFRAX) on the EdFRAX YouTube channel.

To find out more please visit:

[YouTube](https://www.youtube.com/EdFRAX)

[Instagram](https://instagram.com/edfrax)

# NFT minting dapp for ERC-721 A contract

This repo provides a nice and easy way for linking an existing NFT smart contract to this minting dapp. There are two ways of using this repo, you can go the simple route or the more complex one.

The simple route is so simple, all you need to do is download the build folder on the release page and change the configuration to fit your needs. (Follow the video for a walk through).

The more complex route allows you to add additional functionality if you are comfortable with coding in react.js. (Follow the below instructions for a walk through).

## Installation 🛠️

If you are cloning the project then run this first, otherwise you can download the source code on the release page and skip this step.

```sh
git clone {https://github.com/EdFRAX/NFT-Minting-Dapp}
```

Make sure you have node.js installed so you can use npm, then run:

```sh
npm install
```

## Usage ℹ️

In order to make use of this dapp, all you need to do is change the configurations to point to your smart contract as well as update the images and theme file.

For the most part all the changes will be in the `public` folder.

To link up your existing smart contract, go to the `public/config/config.json` file and update the following fields to fit your smart contract, network and marketplace details. The cost field should be in wei.

Note: this dapp is designed to work with the intended NFT smart contract, that only takes one parameter in the mint function "mintAmount". But you can change that in the App.js file if you need to use a smart contract that takes 2 params.

```json
{
  "CONTRACT_ADDRESS": "0xe292A177A270D4620Cbc448C24cB9670187f9Ddf",
  "SCAN_LINK": "https://mumbai.polygonscan.com/address/0xe292A177A270D4620Cbc448C24cB9670187f9Ddf",
  "NETWORK": {
    "NAME": "Mumbai",
    "SYMBOL": "MATIC",
    "ID": 80001
  },
  "OWNER":"NOBODY",
  "YEAR":"2022",
  "NFT_NAME": "EMOJEES",
  "SYMBOL": "EMJ",
  "MAX_SUPPLY": 1024,
  "WEI_COST": 1000000000000000,
  "DISPLAY_COST": 0.001,
  "GAS_LIMIT": 285000,
  "MARKETPLACE": "Opeansea",
  "MARKETPLACE_LINK": "https://testnets.opensea.io/collection/emojees-v2"
}
```

Make sure you copy the contract ABI from remix and paste it in the `public/config/abi.json` file.
(follow the youtube video if you struggle with this part).

Now you will need to create and change 2 images and a gif in the `public/config/images` folder, `1.gif` and `logo.png`.

Next change the theme customization to your liking in the `public/config/theme.css` file.

# I have given a lot of customization in this app, one can easily change size/animation/colors/angles as per his/her wish.

```css


:root {
  /* Body */
  --primary: #ffffff;
  --secondary:#ffffff;
  --bg-angle:147deg;
  --primary-text: #979797;
  --owner:#fd3838;
  --logo:300px;
  
  /* Image preview */
  --img-size:280px;
  --img-radius:10%;
  --img-animation-primary:#fd3838;
  --img-animation-secondary:#ffe53b;
  --animation:spin;
  --animation-showhide:1;
  --animation-shadow:1;

  /*Main container*/
  --main-border:rgba(0, 0, 0, 0);
  --main-rarius:25px;
  --main-bg-primary:#fd3838;
  --main-bg-secondary:#ffe53b;
  --main-angle:147deg;
  --main-text: #ffffff;
  --wallet-text: #101010;

  /*Buttons*/
  --btn-radius:30px;
  --btn-color:#ffffff;
  --btn-text:#fd3838;
  --btn-text-hover:#000000;
  
  /*Buttons*/
  --btn-sec-text:#fd3838;
}
```

Now you will need to create and change the `public/favicon.ico`, `public/logo32.png`, `public/logo192.png`, and
`public/logo512.png` to your brand images.

Remember to update the title and description the `public/index.html` file

```html
<title>Your NFT Collection Name</title>
<meta name="description" content="Mint Your NFT" />
```

Also remember to update the short_name and name fields in the `public/manifest.json` file

```json
{
  "short_name": "SYMBOL",
  "name": "collection_name"
}
```

After all the changes you can run.

```sh
npm run start
```

Or create the build if you are ready to deploy.

```sh
npm run build
```
Now you can host the contents of the build folder on a server.

Or you can make your own repo to deploy this app on [Netlify](https://netlify.app/) like I did.

Thanks.
