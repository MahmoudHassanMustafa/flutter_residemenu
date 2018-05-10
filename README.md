# flutter_residemenu

Residemenu for flutter,android and ios supported

## Screenshot
Android:<br>
![android](https://github.com/peng8350/flutter_residemenu/blob/master/arts/android.gif)<br>
iOS:<br>
![ios](https://github.com/peng8350/flutter_residemenu/blob/master/arts/ios.gif)

## Usage
1.declare in pubspec.yaml

```

dependencies:
  ...

  residemenu:
    ^1.0.0

```

2.create MenuController to OpenMenu,closeMenu,know if menu is Open,listen the menu callback.

```

MenuController _menuController;

void initState(){
   _menuController = new MenuController(
         listener: new MenuListener(
             onClose: (){

             }
             ,
             onOpen: (bool left){

             }

      )
   );

}

```

3.build() method to create my ResideMenu Widget,child is your contentView(if you use MaterialApp,mostly Scaffold)

```

    new ResideMenu(

            decoration: new BoxDecoration(
                image: new DecorationImage(
                    image: new AssetImage("images/menu_background.png"),
                    fit: BoxFit.cover)),
            leftView: buildLeft(),
            controller: _menuController,
            child: ...
            )

```

## Table

| Attribute Name     |     Attribute Explain     | Parameter Type | Default Value  | requirement |
|---------|--------------------------|:-----:|:-----:|:-----:|
| child      | your content View   | Widget   |   null |  necessary |
| direction | The direction of allowing ResideMenu to slide     | enum  | left | optional |
| leftView,rightView | the Menu Content View     | Widget  | null | optional |
| elevation |   Content View shadow | double | 12.0 |optional |
| controller | Control menu behavior, get menu status, monitor menu open, close and other events.   | MenuController | null | optional |
| decoration | use to set bg and color in bottom   | BoxDecoration | null | optional |


## LICENSE

```
MIT License

Copyright (c) 2018 Jpeng

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```