# reactAccordionQuestions
This React project contains a main question with an accordion style drop-down box set format.

Completing this project helped to better reinforce previously studied concepts. 

A general walktrhough of the pertinent React code is given below:

First the data contained in Data.js needs to be iterated. To do this state is used even though the setQuestions state function will never need to be called. The data questions are then iterated over and returns each item as part of the Question component.
```React
function App() {
  const [questions, setQuestions] = useState(data);
  return (
    <main>
      <div className="container">
        <h3>Questions and awnsers about login</h3>
        <section className="info">
          {questions.map((question) => {
            return <SingleQuestion key={question.id} {...question} />;
          })}
        </section>
      </div>
    </main>
  );
}
```


Using the props passed over by SingleQuestion into the Question component the return can be set up.
```React
const Question = ({ title, info }) => {
  return (
    <article className="question">
      <header>
        <h4>{title}</h4>
        <button
          className="btn" >
          btn
        </button>
      </header>
     <p>{info}</p>}
    </article>
  );
};


To set up the toggle button useState() is used.
```React
const Question = ({ title, info }) => {
  const [showInfo, setShowInfo] = useState(false);
  return (
    <article className="question">
      <header>
        <h4>{title}</h4>
        <button
          className="btn">
          btn
        </button>
      </header>
      {showInfo && <p>{info}</p>}
    </article>
  );
};
```


Now the toggle button needs to be set up to show or hide the <p>{info}</p>.
```React
 <button
          className="btn"
          onClick={() => {
            setShowInfo(!showInfo);
          }}
        >
          btn
        </button>
 ```
 
 
 Then set up the btn icons to change depending on if the p.info is showing or not.
 ```React
         <button
          className="btn"
          onClick={() => {
            setShowInfo(!showInfo);
          }}
        >
          {showInfo ? <AiOutlineMinus /> : <AiOutlinePlus />}
        </button>
```

Lastly render to the screen.
```React
ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```


***End walkthrough
```
