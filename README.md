# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts
<!-- 497456958 -->
In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://110.40.240.8:5200/api/](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)


if (item.callback) {
            console.log(item.callback,"item.callback")
            item.callback(this._activeData);
          } else {
            if(item.text === "NO") {
              console.log("No")
              // ???????????? 
              //1.  ?????????????????????????????????Y ?????? ?????? ?????? ??????
              if(data.text.value.slice(-1) === "Y") {
                const shan = data.text.value.split("Y")
                // console.log(shan,"??????")
                // ????????????[]?????????????????????shan[0] // ???????????? Y
                this.lf.updateText(data.id,shan[0] + 'N')
                // this.lf.updateAttributes(data.id, {
                //   properties:'N'
                // });
                 this.lf.setProperties(data.id,{
                  properties:{
                    data:'123'
                  }
              })
                console.log(data,"3")
                return
              }
              // 2.?????? ????????????????????????????????? N ????????? ?????????????????????Y ???????????????
              if(data.text.value.slice(-1) === "N") return
              //3. ?????? N
              // this.lf.updateAttributes(data.id, {
              //   properties:'N'
              // });
              this.lf.setProperties(data.id,{
                SETUP:'123',
                repetition:'1234'
            })
              // ???????????? N
              this.lf.updateText(data.id,data.text.value + '\nN')
              // ??????????????????
              // this.lf.addNode({
              //   type: 'text',
              //   x: data.x,
              //   y: data.y,
              //   id: 20,
              //   text:{
              //     value: 'test',
              //     x: data.x,
              //     y: data.y,
              //   },
              //   properties: {
              //     size: 100,
              //   }
              // })
              return
            }
            console.log("YES")
            // 1. ?????????????????????????????????N 
            if(data.text.value.slice(-1) === "N") {
              console.log(data.text.value.split("N"),"??????")
              const shan = data.text.value.split("N")
              console.log(shan,"??????")
              // ???????????? Y
              this.lf.updateText(data.id,shan[0] + 'Y')
              // ???????????? Y
              this.lf.updateAttributes(data.id, {
                properties:'Y'
              });
              return
            }
            // 2. ????????????????????????????????? Y ????????? ?????????????????????Y ???????????????
            if(data.text.value.slice(-1) === "Y") return
             //3. ?????? Y
             this.lf.updateAttributes(data.id, {
              properties:'Y'
            });
            // ???????????? Y
            this.lf.updateText(data.id,data.text.value + '\nY')
          }
        });
         "@logicflow/core": "^1.1.23",
    "@logicflow/extension": "^1.1.23",