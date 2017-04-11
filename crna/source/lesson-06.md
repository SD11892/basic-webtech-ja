# Expo APIの利用

Expoは様々なラッパーAPIを提供しています。

下記を参照しましょう。

https://docs.expo.io/versions/v15.0.0/sdk/index.html

## Accellerometer

下記のようなコンポーネント用意します。これをApp.jsに組み込みます。

```
import {
  Accelerometer,
} from 'expo';

class TextData extends React.Component {
  constructor() {
    super();
    this.state = {
      data: { x: 0, y: 0, z: 0 },
    };
  }
  componentDidMount() {
    Accelerometer.addListener(data => this.setState({ data }));
  }
  render() {
    return (
      <View>
        <Text>x = {this.state.data.x}</Text>
        <Text>y = {this.state.data.y}</Text>
        <Text>z = {this.state.data.z}</Text>
      </View> 
    );
  } 
}     
```

## 課題

1. 上記の動作を確認する
2. Locationを使ってみる
3. Gyroscopeを使ってみる
