# preact-bs-toast

Bootstrap js with preact simultaneously. Hook and component to use bootstrap toast.  
No build tool needed, just [preact](https://github.com/preactjs/preact) and [hyperscript tagged markup (htm)](https://github.com/developit/htm).

[See an example :arrow_right:](https://thinkawitch.github.io/preact-bs-toast/)

---

### Usage Example


```js
function App() {
    return html`
        <${ToastContextProvider}>
            <div class="card">
                <${DemoComponent} />
            </div>
            <${ToastHolder} position="bottom-right" />
        <//>
    `;
}

function DemoComponent() {
    const { addToast, removeToast, toastId } = useToast();
    const showToast = () => {
        addToast({ 
            icon: 'bi-sun', title: 'Always sunny', 
            message: "It's always sunny in California", 
            type: 'warning', delay: 10000 
        });
    }
    return html`
        <div class="card-body">
            <button class="btn btn-primary" onClick=${showToast}>toast</button>
        </div>
    `;
}
```

