#  React-Remarkable


[https://facebook.github.io/react/](https://facebook.github.io/react/)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Markdown</title>
</head>
<body>
    <div id="box">
        <!-- show -->
    </div>
    <div id="mountNode">
        <!-- show -->
    </div>
    <div>
        <h1> Markdown ??? Using External Plugins: remarkable, an external Markdown library.</h1>
        <a href="https://facebook.github.io/react/ ">https://facebook.github.io/react/ </a>
    </div>
    <script src="./libs/react.js"></script>
    <script src="./libs/react-dom.js"></script>
    <script src="./libs/browser.js"></script>
    <script src="./libs/remarkable.min.js"></script>
    <script type="text/babel" src="markdown.jsx"></script>
</body>
</html>
``` 


```jsx
// https://facebook.github.io/react/
// ?? Using External Plugins: remarkable, an external Markdown library.
class MarkdownEditor extends React.Component {
  constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
    this.state = {value: 'Type some *markdown* here!'};
  }

  handleChange() {
    this.setState({value: this.refs.textarea.value});
  }

  getRawMarkup() {
    var md = new Remarkable();
    return { __html: md.render(this.state.value) };
  }

  render() {
    return (
      <div className="MarkdownEditor">
        <h3>Input</h3>
        <textarea
          onChange={this.handleChange}
          ref="textarea"
          defaultValue={this.state.value} />
        <h3>Output</h3>
        <div
          className="content"
          dangerouslySetInnerHTML={this.getRawMarkup()}
        />
      </div>
    );
  }
}

ReactDOM.render(<MarkdownEditor />, mountNode);
``` 









