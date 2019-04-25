# React_Native_Dropdown_Menu


1.Install react-native-popup-menu by  
```diff
- npm install react-native-popup-menu --save    
```

2.Through react-native  packages import all required components.
```diff
import React, { Component } from "react";
import { Platform, StyleSheet, Text, View, Alert, YellowBox} from "react-native";
import { Menu, MenuProvider, MenuOptions, MenuOption, MenuTrigger} from "react-native-popup-menu";
```   


3.Create constructor in your HomeActivity class with props parameter and Create super method with props parameter in constructor.
```diff
constructor(props) {
     super(props);
     YellowBox.ignoreWarnings([
      'Warning: isMounted(...) is deprecated', 'Module RCTImageLoader'
    ]);
   }
```


4. Implement render method and return Menu component wrapped by MenuProvider component. check below component structure for dropdown menu.

```diff
render() {
    return (
      <MenuProvider style={{ flexDirection: "column", padding: 30 }}>
        <Menu onSelect={value => alert(`You Clicked : ${value}`)}>

          <MenuTrigger  >
          <Text style={styles.headerText}>DropDown Menu</Text>
          </MenuTrigger  >

          <MenuOptions>
            <MenuOption value={"EditProfile"}>
              <Text style={styles.menuContent}>EditProfile</Text>
            </MenuOption>
            <MenuOption value={"About"}>
              <Text style={styles.menuContent}>About</Text>
            </MenuOption>
            
            <MenuOption value={"Logout"}>
              <Text style={styles.menuContent}>Logout</Text>
            </MenuOption>
            <MenuOption value={3} disabled={true}>
              
            </MenuOption>
          </MenuOptions>

        </Menu>
      </MenuProvider>
    );
  }
}
```


5.Apply the below style sheet design.
```diff
const styles = StyleSheet.create({
    headerText: {
    fontSize: 20,
    margin: 10,
    fontWeight: "bold"
  },
  menuContent: {
    color: "#000",
    fontWeight: "bold",
    padding: 2,
    fontSize: 20
  }
});

```

## Complete Source Code for App.js 

```diff
import React, { Component } from "react";
import { Platform, StyleSheet, Text, View, Alert, YellowBox} from "react-native";
import { Menu, MenuProvider, MenuOptions, MenuOption, MenuTrigger} from "react-native-popup-menu";

export default class HomeActivity extends Component {

  constructor(props) {
     super(props);
     YellowBox.ignoreWarnings([
      'Warning: isMounted(...) is deprecated', 'Module RCTImageLoader'
    ]);
   }

  render() {
    return (
      <MenuProvider style={{ flexDirection: "column", padding: 30 }}>
        <Menu onSelect={value => alert(`You Clicked : ${value}`)}>

          <MenuTrigger  >
          <Text style={styles.headerText}>DropDown Menu</Text>
          </MenuTrigger  >

          <MenuOptions>
            <MenuOption value={"EditProfile"}>
              <Text style={styles.menuContent}>EditProfile</Text>
            </MenuOption>
            <MenuOption value={"About"}>
              <Text style={styles.menuContent}>About</Text>
            </MenuOption>
            
            <MenuOption value={"Logout"}>
              <Text style={styles.menuContent}>Logout</Text>
            </MenuOption>
            <MenuOption value={3} disabled={true}>
              
            </MenuOption>
          </MenuOptions>

        </Menu>
      </MenuProvider>
    );
  }
}

const styles = StyleSheet.create({
    headerText: {
    fontSize: 20,
    margin: 10,
    fontWeight: "bold"
  },
  menuContent: {
    color: "#000",
    fontWeight: "bold",
    padding: 2,
    fontSize: 20
  }
});
```

