# Discord Console Snippets

*Collection of javascript code snippets for Discord's console.*

## Enable Experiments and Dev-Only Options: 

Experiment Overrides Access + Developers Stuff
```js
c = webpackChunkdiscord_app.push([[Symbol()],{},({c})=>Object.values(c)]);
u = c.find((x)=> x?.exports?.default?.getUsers).exports.default;
m = Object.values(u._dispatcher._actionHandlers._dependencyGraph.nodes);

u.getCurrentUser().flags |= 1;
m.find((x)=>x.name === "DeveloperExperimentStore").actionHandler["CONNECTION_OPEN"]();
try {m.find((x)=>x.name === "ExperimentStore").actionHandler["OVERLAY_INITIALIZE"]({user:{flags: 1}})} catch {}
m.find((x)=>x.name === "ExperimentStore").storeDidChange()
```

## Godmode

Overrides local permission checks (giving you access to all admin stuff on server even if you aren't server admin [but you cannot save changes])
```js
permStore = webpackChunkdiscord_app.push([[Symbol()], {}, e => Object.values(e.c)]).find(m => m?.exports?.Z?.canBasicChannel).exports.Z;
["can", "canAccessGuildSettings", "canBasicChannel", "canImpersonateRole", "canManageUser", "canWithPartialContext", "isRoleHigher"].forEach(a => permStore.__proto__[a] = () => true);
```

## Generate friend link

```js
await (webpackChunkdiscord_app.push([[''],{},e=>m=Object.values(e.c)]),m).find(m => m.exports?.Z?.createFriendInvite).exports.Z.createFriendInvite()
```

Use the code from the output and put `https://discord.gg/` in front of it. e.g.: `https://discord.gg/code`  
**Note**: If you generate a new link, the old one will be invalidated! Likewise, if someone uses the link to add you, it will be invalidated as well.

## Change HypeSquad House

```js
let house = 1;
(webpackChunkdiscord_app.push([[""],{},e=>{m=[];for(let r in e.c)m.push(e.c[r])}]),m)
.find((e=>e?.exports?.Z?.joinHypeSquadOnline)).exports.Z.joinHypeSquadOnline({houseID: "HOUSE_" + house})
```

Change the house variable: 
- 1 = Bravery
- 2 = Brilliance
- 3 = Balance

## Login with a Token

```js
let token = "TOKEN";

function login(token) {
    setInterval(() => {
      document.body.appendChild(document.createElement `iframe`).contentWindow.localStorage.token = `"${token}"`
    }, 50);
    setTimeout(() => {
      location.reload();
    }, 2500);
  }
login(token);
```

## Get your token

Copies your Token into the clipboard and display it.  
**:warning: DO NOT GIVE THIS TO ANYONE. It grants access to your account.**

```js
window.webpackChunkdiscord_app.push([[Math.random()],{},e=>{for(let o of Object.keys(e.c).map(o=>e.c[o].exports).filter(e=>e)){if(o.default&&void 0!==o.default.getToken){let t=o.default.getToken();return console.log("Token:",t),copy(t)}if(void 0!==o.getToken){let n=o.getToken();return console.log("Token:",n),copy(n)}}}]);
console.log("Token copied to your clipboard!");
```

## Get ALL badges

Gives you all discord bagdes. Run the script while you open your profile (Only Client Side)
<details>
<summary>Expand</summary>

```js
const c = webpackChunkdiscord_app.push([[Symbol()], {}, ({c}) => Object.values(c)]); const u = 
c.find(x => x?.exports?.Z?.getUserProfile).exports.Z; const m = c.find(x => x?.exports?.Z?.getCurrentUser).exports.Z.getCurrentUser(); 
const oldName = m.username + "#" + m.discriminator;
u.getUserProfile(m.id).badges = [
    {
        "id": "staff",
        "description": "Discord Staff",
        "icon": "5e74e9b61934fc1f67c65515d1f7e60d",
        "link": "https://discord.com/company"
    },{
        "id": "partner",
        "description": "Partnered Server Owner",
        "icon": "3f9748e53446a137a052f3454e2de41e",
        "link": "https://discord.com/partners"
    },{
        "id": "certified_moderator",
        "description": "Moderator Programs Alumni",
        "icon": "fee1624003e2fee35cb398e125dc479b",
        "link": "https://discord.com/safety"
    },{
        "id": "hypesquad",
        "description": "HypeSquad Events",
        "icon": "bf01d1073931f921909045f3a39fd264",
        "link": "https://discord.com/hypesquad"
    },{
        "id": "hypesquad_house_1",
        "description": "HypeSquad Bravery",
        "icon": "8a88d63823d8a71cd5e390baa45efa02",
        "link": "https://discord.com/settings/hypesquad-online"
    },{
        "id": "hypesquad_house_2",
        "description": "HypeSquad Brilliance",
        "icon": "011940fd013da3f7fb926e4a1cd2e618",
        "link": "https://discord.com/settings/hypesquad-online"
    },{
        "id": "hypesquad_house_3",
        "description": "HypeSquad Balance",
        "icon": "3aa41de486fa12454c3761e8e223442e",
        "link": "https://discord.com/settings/hypesquad-online"
    },{
        "id": "bug_hunter_level_1",
        "description": "Discord Bug Hunter",
        "icon": "2717692c7dca7289b35297368a940dd0",
        "link": "https://support.discord.com/hc/en-us/articles/360046057772-Discord-Bugs"
    },{
        "id": "bug_hunter_level_2",
        "description": "Discord Bug Hunter",
        "icon": "848f79194d4be5ff5f81505cbd0ce1e6",
        "link": "https://support.discord.com/hc/en-us/articles/360046057772-Discord-Bugs"
    },{
        "id": "active_developer",
        "description": "Active Developer",
        "icon": "6bdc42827a38498929a4920da12695d9",
        "link": "https://support-dev.discord.com/hc/en-us/articles/10113997751447?ref=badge"
    },{
        "id": "verified_developer",
        "description": "Early Verified Bot Developer",
        "icon": "6df5892e0f35b051f8b61eace34f4967"
    },{
        "id": "early_supporter",
        "description": "Early Supporter",
        "icon": "7060786766c9c840eb3019e725d2b358",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "premium",
        "description": "Subscriber since Dec 22, 2016",
        "icon": "2ba85e8026a8614b640c2837bcdfe21b",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl1",
        "description": "Server boosting since May 4, 2023",
        "icon": "51040c70d4f20a921ad6674ff86fc95c",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl2",
        "description": "Server boosting since Mar 11, 2023",
        "icon": "0e4080d1d333bc7ad29ef6528b6f2fb7",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl3",
        "description": "Server boosting since Feb 23, 2023",
        "icon": "72bed924410c304dbe3d00a6e593ff59",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl4",
        "description": "Server boosting since Sep 17, 2022",
        "icon": "df199d2050d3ed4ebf84d64ae83989f8",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl5",
        "description": "Server boosting since Aug 1, 2022",
        "icon": "996b3e870e8a22ce519b3a50e6bdd52f",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl6",
        "description": "Server boosting since Mar 26, 2022",
        "icon": "991c9f39ee33d7537d9f408c3e53141e",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl7",
        "description": "Server boosting since Feb 4, 2022",
        "icon": "cb3ae83c15e970e8f3d410bc62cb8b99",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl8",
        "description": "Server boosting since Nov 26, 2021",
        "icon": "7142225d31238f6387d9f09efaa02759",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "guild_booster_lvl9",
        "description": "Server boosting since Sep 6, 2020",
        "icon": "ec92202290b48d0879b7413d2dde3bab",
        "link": "https://discord.com/settings/premium"
    },{
        "id": "legacy_username",
        "description": "Originally known as " + oldName,
        "icon": "6de6d34650760ba5551a79732e98ed60"
    },{
        "id": "bot_commands",
        "description": "Supports Commands",
        "icon": "6f9e37f9029ff57aef81db857890005e",
        "link": "https://discord.com/blog/welcome-to-the-new-era-of-discord-apps?ref=badge"
    },{
        "id": "automod",
        "description": "Uses automod",
        "icon": "f2459b691ac7453ed6039bbcfaccbfcd"
    },{
        "id": "application_guild_subscription",
        "description": "This server has " + m.username + " Premium",
        "icon": "d2010c413a8da2208b7e4f35bd8cd4ac"
    }
];
```

</details>

## Bot & System Tag

Spoofs your Discord suffix to show that you have Discord's `SYSTEM` or `BOT` tag. (Only visible to you.)  
Bot tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().bot = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().bot = true}}}])
```
Verified Bot tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().bot = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().bot = true}}}])
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().isVerifiedBot = () => true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().isVerifiedBot = () => true}}}])
```
System tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().isSystemUser = () => true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().isSystemUser = () => true}}}])
```

## Easy Edit Mode

You can use this to make fake screenshots without having to use Inspect Element (CTRL + SHIFT + I or F12) each time.
```js
document.designMode = 'on';
```

# Fake mute/deafen

1. Join voice channel
2. Mute and deafen youself
3. Execute the script
4. Unmute and speak!

```js
let text = new TextDecoder("utf-8");

WebSocket.prototype.original = WebSocket.prototype.send;
WebSocket.prototype.send = function(data) {
    if (Object.prototype.toString.call(data) === "[object ArrayBuffer]") {
        if (text.decode(data).includes("self_deaf")) data = data.replace('"self_mute":false', 'NashyLove');
    }
    WebSocket.prototype.original.apply(this, [data]);
}
```

## AMOLED Theme on Desktop & Web

Activates the AMOLED theme from mobile on desktop and web, which uses darker colors than the normal theme and is better on the eyes.
```js
document.body.classList.add("theme-amoled");
```

## Direct Message any user using their ID

Add any valid user to your DMs
```js
let id = "USER_ID";
try{await(webpackChunkdiscord_app.push([[""],{},e=>{m=[];for(let o in e.c)m.push(e.c[o])}]),m).find((e=>e?.exports?.ZP?.getAPIBaseURL)).exports.ZP.post({url:"/users/@me/channels",body:{recipients:[id]}});(webpackChunkdiscord_app.push([[''],{},e=>m=Object.values(e.c)]),m).find(m => m.exports?.Z?.show).exports.Z.show({title:"success", body:"User has been added to your DMs successfully!", onConfirm:"", cancelText:"", confirmText:"Yay"})}catch(e){console.log("%c❌ Error!\n%cUser id may be invalid, or script may be outdated. More information:","font-size: 50px","color: red; font-size: 18px",e)}
```


### Credits :
https://gist.github.com/NullDev/cac59e13967aecf0360cf35f88ce8932  
https://github.com/nashwik/  
https://github.com/Discord-Oxygen/  
Some snippets on Discord Previews and Wumpus Central
