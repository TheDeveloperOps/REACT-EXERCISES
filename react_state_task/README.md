# STATE HANDLING TASKS 

**1. Use React state to change the background of the page. You can use this technique to apply a dark mode for your portfolio.**

![Alt text](image-1.png)
![Alt text](image-2.png)

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <style>
        .container{
            border-radius: 10px;
            height: 470px;
            width: 80%;
            display: block;
            background: linear-gradient(
                60deg,
                #f79533,
                #f37055,
                #ef4e7b,
                #a166ab,
                #5073b8,
                #1098ad,
                #07b39b,
                #6fba82
            );
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        img{
            border-radius: 50;
        }
        .boxed *{
            text-align: center;
            margin-left: 20px;
            float: left;
            margin-top: 10px;
            border-radius: 3px;
            background-color: rgb(37, 203, 224);
            border: 2px solid rgb(37, 203, 224) ;
            width: 70px;
        }
        .light-mode *{
            background: #fff;
            color: #000;
        }
        .dark-mode *{
            background: #222;
            color: #fff;
        }
        .bn29 {
            margin-top: 20px;
            margin-left: 75%;
            border: none;
            padding: 0.8em 2.5em;
            outline: none;
            color: white;
            font-style: 1.2em;
            position: absolute;
            z-index: 1;
            cursor: pointer;
            background: none;
            text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.45);
            }

            .bn29:before,
            .bn29:after {
            position: absolute;
            top: 50%;
            left: 50%;
            border-radius: 10em;
            -webkit-transform: translateX(-50%) translateY(-50%);
            transform: translateX(-50%) translateY(-50%);
            width: 105%;
            height: 105%;
            content: "";
            z-index: -2;
            background-size: 400% 400%;
            background: linear-gradient(
                60deg,
                #f79533,
                #f37055,
                #ef4e7b
                /* #a166ab,
                #5073b8,
                #1098ad,
                #07b39b,
                #6fba82 */
            );
            }

            .bn29:before {
            -webkit-filter: blur(7px);
            filter: blur(7px);
            -webkit-transition: all 0.25s ease;
            transition: all 0.25s ease;
            -webkit-animation: pulse 10s infinite ease;
            animation: pulse 10s infinite ease;
            }

            .bn29:after {
            -webkit-filter: blur(0.3px);
            filter: blur(0.3px);
            }

            .bn29:hover:before {
            width: 115%;
            height: 115%;
            }
    </style>
</head>
<body>
    <div id="app"></div>
    <script type="text/babel">
        const ShowCard=()=>{
            return(
                <div>
                    <img src="./jagan.jpg" width={150} style={{borderRadius:'50%',paddingTop:25,paddingLeft:30}}/>
                    <h1  style={{fontSize:30,paddingLeft:40}}>JAGAN T<img src='./tick.png' width={25} style={{paddingLeft:10}}/></h1>
                    <h2 style={{fontSize:15,paddingLeft:20}}> MERN STACK DEVELOPER</h2>
                    <h1 style={{fontSize:30,paddingLeft:40}}>SKILLS</h1>
                    <div className='boxed'>
                    <div>HTML</div><div>CSS</div><div>JS</div><div>REACT</div><div>PYTHON</div><div>MYSQL</div><div>JAVA</div><div>REDUX</div>
                    </div>
                    </div>
            )
        }
      const Portfolio = () => {
        const [darkMode, setDarkMode] = React.useState(false);
  
        const toggleDarkMode = () => {
          setDarkMode(!darkMode);
        };
  
        React.useEffect(() => {
          const bodyElement = document.querySelector('body');
          if (darkMode) {
            bodyElement.classList.add('dark-mode');
          } else {
            bodyElement.classList.remove('dark-mode');
          }
        }, [darkMode]);
  
        return (
          <div className='container'>
            <button onClick={toggleDarkMode} className='bn29'>
              {darkMode ? 'Light Mode' : 'Dark Mode'}
            </button>
            <ShowCard/>
          </div>
        );
      };
  
      const rootElement = ReactDOM.createRoot(document.getElementById('app'));
      rootElement.render(<Portfolio />);
    </script>
  </body>
</html>
```
*Output of the above*
![Alt text](image-3.png)
![Alt text](image-4.png)