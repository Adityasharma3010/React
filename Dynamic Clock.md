```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>React</title>
  </head>

  <body>
    <div id="root">
      <script
        src="https://unpkg.com/react@18/umd/react.development.js"
        crossorigin
      ></script>
      <script
        src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
        crossorigin
      ></script>
      <script>
        function MyApp() {
          const [time, setTime] = React.useState(
            new Date().toLocaleTimeString()
          );

          React.useEffect(() => {
            setInterval(() => {
              setTime(new Date().toLocaleTimeString());
            }, 1000);
          }, []);

          return React.createElement("header", null, `Hello World! ${time}`);
        }

        const root = ReactDOM.createRoot(document.getElementById("root"));
        root.render(React.createElement(MyApp));
      </script>
    </div>
  </body>
</html>
