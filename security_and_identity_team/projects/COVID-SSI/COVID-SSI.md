# COVID Self-Sovereign Identity

### Objectives

<figure><figure><iframe src="https://player.vimeo.com/video/305420834?title=0&amp;byline=0" width="640" height="360" allowfullscreen=""></iframe></figure></figure>


- To provide <b>free-education around SSI </b> to COVID app makers.
- To provide <b>open-source SSI tools</b> for COVID App makers to use.

## Free Education

We will be working with the writing team at OpenMined to create blog posts aimed at lowering the barrier of entry into SSI for developers. If you'd like to write a blogpost, reach out on the Slack! We are also working with members of the Sovrin foundation to produce useful learning material.


## Open Source Tools

The technical branch of this project is to extend Opus with self-sovereign identity (SSI) functionality like token issuance and verification. Once this is established, we can run Opus SSO services purely on the basis of the proof certificates provided by users,
In the long term we can also use this to aggregate information from online identities and issue these attributes as verifiable credentials to Opus users. This allows users to participate in other SSI learning applications with information that has previously been verified and attested to by Opus. We can use CL signatures to allow users to prove their data is 'correct' without a remote SSI application ever knowing its value. The remote SSI application can send their model to the user to learn their data. If, as Opus, we also issue noised data credentials then we can train differentially private models on verifiably correct data which never leaves the control of the user.

<img src="images/endgame.png " alt="SSI Open Data Market" width="1000"/>


However, to begin with, we're not going that deep. We want to be able to provide SSO services to anyone who presents valid credentials for doing so. That means Opus hardly needs to store any information about it's users. All it needs to know when vouching for users to third-party organisations is the bare minimum and that can be verified through credentials presnted by the user at the time of requesting that service, not necessarily database.If Opus has previously signed off the valid credential, it's as good as it being taken from database controlled by Opus. To achieve this integration we are doing two projects things in parallel:

### A - Long Term: Build a completely open-source HL-Aries set up with our own open-source controller.
<img src="images/PlanA.png " alt="Long Term" width="1000"/>

<b>More on Plan A coming soon... </b>

### B - Short Term: Implement a very quick proof-of-concept using StreetCred
<img src="images/PlanB.png " alt="Short Term" width="1000"/>

#### Flows

- <b><a href="B/create-account.pdf">Flow 1: Create an Account</a>
- <a href="B/login-ssi.pdf">Flow 2: Log in to Account for SSO Services</a></b>
