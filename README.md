<div align="center">
 <img width="400" valign="top" src="https://assets.seerbitapi.com/images/icon.png">
</div>

<h1 align="center">
  <img width="60" valign="bottom" src="https://reactnative.dev/img/header_logo.svg" alt="ReactJS">
   SeerBit
</h1>

# Seerbit Checkout Wrapper for ReactJS

# Requirements
This module was built and tested using React 15.0.0 - 18.0.0

## Get Started

A simple way to add Seerbit to your React application

[![NPM](https://img.shields.io/npm/v/react-seerbit.svg)](https://www.npmjs.com/package/seerbit-reactjs) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Install

```bash
npm install --save seerbit-reactjs
```

## Usage

```jsx
import React, { Component } from "react";
import SeerbitCheckout from "seerbit-reactjs"

export default class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      public_key: "YOUR_API_KEY",
      amount: 100,
      tranref: new Date().getTime(),
      customization: {
        theme: {
          border_color: "#000000",
          background_color: "#004C64",
          button_color: "#0084A0",
        },
        payment_method: ["card", "account", "transfer", "wallet", "ussd"],
        display_fee: true, // true 
        display_type: "embed", //inline
        logo: "logo_url | base64", 
      }
    };
  }

  close = (close) => {
    console.log(close);
  };
  callback = (response) => {
    console.log(response);
  };

  checkProgress = (progress)=>{
    console.log(progress)
  }
  render() {
  
    return (
      <SeerbitCheckout
        className="btn seerbit-btn"
        type='div'
        tranref={this.state.tranref}
        currency={"NGN"}
        description={"shopping"}
        country={"NG"}
        public_key={this.state.public_key}
        callback={this.callback}
        close={this.close}
        scriptStatus={this.checkProgress}
        amount={this.state.amount}
        tag={"button"}
        full_name={"James Brown"}
        email={"a@b.com"}
        mobile_no={"00000000000"}
        customization={this.state.customization}
        version={"2"}//optional
        title={'Pay with SeerBit'}
      />
    );
  }
}

```

Please checkout <a href='https://doc.seerbit.com'>Seerbit Documentation</a> for other available options you can add to the tag

## License

MIT © [seerbit](https://github.com/seerbit)
