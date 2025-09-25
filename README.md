# HyperText Query Language (HTQL)

> **What if HTML could natively express logic, structure, and interactivity—without JavaScript frameworks?**  
> *HTQL brings logic, templating, and data binding directly into your markup—without the baggage.*

---

## 🚀 The Vision

**HTQL** extends HTML with native control flow and component inclusion—no build tools, no frameworks, no complexity. Just write HTML that works the way it always should have.

```htql
<!-- This should just work, right? -->
<include src="./header.htql" />

<main>
  <if cond="user.loggedIn">
    <h1>Welcome back, <span data-bind="user.name">!</span></h1>

    <repeat each="post in posts">
      <article>
        <h2 data-bind="post.title"></h2>
        <p data-bind="post.excerpt"></p>
      </article>
    </repeat>
  <else>
    <h1>Please <a href="/login">sign in</a> to continue</h1>
  </if>
</main>

<include src="./footer.htql" />
```

**HTQL is designed for clarity, composability, and true declarative power.**

---

## 💡 Why HTQL?

### The Problem
- **HTML lacks composability**: No native way to include components or add logic
- **Modern frameworks are overkill**: React/Vue for simple sites? Really?
- **Build tools are exhausting**: Webpack, Vite, Rollup... just to include a header?
- **PHP had it right**: `<?php include 'header.php' ?>` was brilliant, but server-only

### The Solution
HTQL brings the best of PHP's simplicity to modern client-side development:

- ✅ **Native includes**: `<include src="component.htql" />`
- ✅ **Control flow**: `<if>`, `<else>`, `<repeat>`, `<while>`
- ✅ **Data binding**: `data-bind="user.name"`
- ✅ **Zero build step**: Runs directly in the browser
- ✅ **Progressive enhancement**: Starts as static HTML, becomes interactive
- ✅ **AI-friendly**: Clean, semantic syntax that AI tools love

---

## 🎯 Core Features

### 🧩 Component Inclusion
```htql
<include src="./components/user-profile.htql" />
<include src="https://cdn.example.com/widgets/weather.htql" />
```

### 🔀 Control Flow
```htql
<if cond="user.role === 'admin'">
  <button>Delete All Users</button>
<else>
  <p>Access denied</p>
</if>

<repeat each="item in shoppingCart">
  <li>
    <span data-bind="item.name"></span> - 
    <strong data-bind="item.price | currency"></strong>
  </li>
</repeat>
```

### 📊 Data Binding
```htql
<!-- Simple binding -->
<h1 data-bind="pageTitle"></h1>

<!-- Two-way binding -->
<input data-sync="user.email" type="email" />

<!-- Computed values -->
<span data-bind="items.length"> items in cart</span>
```

### 🎪 Event Handling
```htql
<button onclick="addToCart(product.id)">Add to Cart</button>
<form onsubmit="saveUser()" data-redirect="/dashboard">
  <!-- form fields -->
</form>
```

---

## 🏗️ Architecture

HTQL works with a simple runtime that:

1. **Parses** HTQL tags in your HTML
2. **Processes** control flow and includes
3. **Binds** data to elements
4. **Updates** the DOM reactively

```
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│  Your Page  │───▶│ HTQL Runtime │───▶│   Browser   │
│   + HTQL    │    │   (HTQL.js)  │    │    DOM      │
└─────────────┘    └──────────────┘    └─────────────┘
```

**No compiler. No transpiler. Runs directly in the browser.**

---

## 📚 Quick Start

### 1. Add the Runtime
```html
<!-- Coming Soon -->
```

### 2. Use HTQL Tags
```htql
<include src="./components/navbar.htql" />

<main>
  <if cond="products.length > 0">
    <repeat each="product in products">
      <div class="product-card">
        <h3 data-bind="product.name"></h3>
        <p data-bind="product.description"></p>
        <button onclick="buyNow(product.id)">Buy Now</button>
      </div>
    </repeat>
  <else>
    <p>No products available</p>
  </if>
</main>
```

### 3. Provide Data
```js
htql.setData({
  products: [
    { id: 1, name: "Cool Widget", description: "It's very cool" },
    { id: 2, name: "Hot Gadget", description: "It's very hot" }
  ]
});
```

That's it! No build tools, no complicated setup.

---

## 🎨 Examples

### Simple Blog
```htql
<include src="./header.htql" />

<main>
  <repeat each="post in blogPosts">
    <article>
      <h1 data-bind="post.title"></h1>
      <time data-bind="post.publishedAt | date"></time>
      <div data-bind="post.content | markdown"></div>
    </article>
  </repeat>
</main>

<include src="./footer.htql" />
```

### Dashboard with Authentication
```htql
<if cond="user.isAuthenticated">
  <include src="./admin-dashboard.htql" />
<else>
  <include src="./login-form.htql" />
</if>
```

### E-commerce Product List
```htql
<div class="filters">
  <input data-sync="searchQuery" placeholder="Search products..." />
  <select data-sync="categoryFilter">
    <option value="">All Categories</option>
    <repeat each="category in categories">
      <option data-bind-value="category.id" data-bind="category.name"></option>
    </repeat>
  </select>
</div>

<div class="products">
  <repeat each="product in filteredProducts">
    <div class="product">
      <img data-bind-src="product.image" data-bind-alt="product.name" />
      <h3 data-bind="product.name"></h3>
      <p data-bind="product.price | currency"></p>
      <button onclick="addToCart(product.id)">Add to Cart</button>
    </div>
  </repeat>
</div>
```

---

## 🚧 Development Status

**Current Status**: 🏗️ In Active Development

### ✅ Planned Features
- [x] Project concept and architecture
- [ ] Core runtime engine
- [ ] `<include>` tag implementation
- [ ] `<if>`/`<else>` conditional rendering
- [ ] `<repeat>` loops
- [ ] Data binding (`data-bind`, `data-sync`)
- [ ] Event handling
- [ ] VS Code extension
- [ ] Documentation site
- [ ] Tutorial series

---

## 🤝 Contributing

HTQL is being built in public! We welcome contributors of all skill levels.

### Ways to Help
- 🐛 Report bugs and edge cases
- 💡 Suggest features that would make HTQL better
- 🧪 Test early versions and provide feedback
- 📖 Write documentation and examples
- 🛠️ Submit pull requests for new features

### Getting Started
1. Fork this repository
2. Check out our [Contributing Guide](CONTRIBUTING.md)
3. Join our [Discord community](https://discord.gg/hRcng2DZQ4)
4. Start with issues labeled `good-first-issue`

---

## 🤔 FAQ

### How is this different from htmx?
- **htmx** enhances HTML with server-side interactions
- **HTQL** enhances HTML with client-side logic and components
- They solve different problems and can work together!

### Does this work with existing frameworks?
Yes! HTQL can progressively enhance static HTML or work alongside React, Vue, etc.

### What about SEO?
HTQL starts as static HTML, so it's SEO-friendly by default. Server-side rendering support is planned.

### Browser support?
Modern browsers (Chrome 80+, Firefox 75+, Safari 13+, Edge 80+). IE11 support is not planned.

---

## 📜 License

MIT License - see [LICENSE](LICENSE) for details.

---

**Built with ❤️ by developers who believe HTML deserves better.**  
📫 hello@HTQL.org | 💬 [Join the Discord](https://discord.gg/hRcng2DZQ4)
