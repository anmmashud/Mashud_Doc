# 🎓 3-Month Self-Mastery Plan — BornoType Developer Roadmap

> **Goal:** Become fully independent in building, debugging, upgrading, and deploying the BornoType application (and similar web apps) — without any AI assistance.

> [!TIP]
> You said you learn best by doing projects. Each week includes a **🔨 Mini-Project** that directly maps to a part of BornoType. By Week 12, you'll rebuild the entire app from scratch.

---

## 📊 Skills You Need (Mapped from Your Project)

| Skill Area | Where It's Used in BornoType |
|---|---|
| **Python Core** | `converter/engine.py`, `converter/keymap.py`, `converter/util.py` |
| **Flask** | `app.py` — routes, templates, JSON API |
| **HTML5** | `templates/index.html` — structure, semantic elements |
| **CSS3** | `static/css/style.css` — theming, responsive, animations |
| **JavaScript (Vanilla)** | `index.html <script>` — DOM, Fetch API, Clipboard API |
| **Unicode & Text Processing** | Bengali character classification, encoding conversion |
| **Git & Version Control** | Project management, collaboration |
| **Debugging & DevTools** | Browser console, Python debugger |
| **Deployment** | Getting the app live on the internet |
| **Testing** | `test_script.py` — ensuring correctness |

---

## 🗓️ MONTH 1 — Foundations (Weeks 1–4)

### Week 1: Python Fundamentals

**Topics:**
- Variables, data types (strings, lists, dicts, tuples)
- Conditionals (`if/elif/else`)
- Loops (`for`, `while`) — *your engine.py uses `while` loops heavily*
- Functions and return values
- String methods: `.replace()`, `.join()`, slicing `[2:]`
- f-strings for formatting

**🔨 Mini-Project:** Write a program that takes a sentence and classifies each character as "vowel", "consonant", "digit", or "other" — similar to how `engine.py` classifies Bengali characters.

**📚 Resources:**
- [Python Official Tutorial](https://docs.python.org/3/tutorial/) — Chapters 1–5
- [Automate the Boring Stuff](https://automatetheboringstuff.com/) — Chapters 1–6 (free online)
- Practice: [HackerRank Python](https://www.hackerrank.com/domains/python)

---

### Week 2: Python Intermediate + OOP

**Topics:**
- Classes and objects (`class Unicode` in your engine)
- `self` keyword and instance methods
- `__init__` constructor
- Modules and packages (`from .keymap import ...`)
- `__init__.py` and how Python packages work
- File I/O (reading/writing files)
- List comprehensions
- Error handling: `try/except/finally`
- Regular expressions (`re` module) — *used in your `app.py`*

**🔨 Mini-Project:** Create a `TextAnalyzer` class with methods like `is_uppercase()`, `is_digit()`, `count_words()`. Make it a proper Python package with `__init__.py`.

**📚 Resources:**
- [Real Python — OOP](https://realpython.com/python3-object-oriented-programming/)
- [Real Python — Regex](https://realpython.com/regex-python/)
- [Python re module docs](https://docs.python.org/3/library/re.html)

---

### Week 3: HTML & CSS Foundations

**Topics:**
- HTML5 semantic elements: `<header>`, `<main>`, `<footer>`, `<section>`, `<details>`
- Forms: `<textarea>`, `<input>`, `<button>`, `<label>`
- Attributes: `id`, `class`, `contenteditable`, `placeholder`
- CSS selectors (element, class, id, pseudo-classes like `:focus`, `:hover`, `::before`)
- Box model: margin, padding, border
- CSS custom properties (CSS variables) — *your `style.css` uses `:root` variables extensively*
- Colors: hex, rgba, HSL
- Typography: Google Fonts, `font-family` stacks

**🔨 Mini-Project:** Build a static "note-taking" page with a header, two text panels side by side, a footer, and a dark/light color scheme using only CSS variables (similar to BornoType's layout).

**📚 Resources:**
- [MDN HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/HTML)
- [MDN CSS First Steps](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)
- [CSS Variables Guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [Google Fonts](https://fonts.google.com/)

---

### Week 4: CSS Intermediate — Layout, Responsive, Animations

**Topics:**
- Flexbox (you use it everywhere: `.converter-board`, `.panel-header`, `.controls`)
- CSS Grid basics
- Media queries: `@media (min-width: 900px)` — *your app uses this*
- Transitions: `transition: all 0.2s ease` — *used in your buttons & panels*
- Keyframe animations: `@keyframes pulse` — *used for loading state*
- Pseudo-elements: `::before`, `::after` — *used in your instructions chevron*
- `data-*` attributes for theming: `[data-theme="dark"]`
- Toggle switch styling (pure CSS) — *your auto-convert switch*

**🔨 Mini-Project:** Recreate BornoType's entire CSS from scratch. Include: two-panel responsive layout, dark/light theme toggle via `data-theme`, animated toggle switch, toast notification, and the collapsible instructions section.

**📚 Resources:**
- [CSS Tricks — Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks — Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [MDN Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries)
- [Web.dev — Responsive Design](https://web.dev/responsive-web-design-basics/)

---

## 🗓️ MONTH 2 — Core Application Skills (Weeks 5–8)

### Week 5: JavaScript Fundamentals

**Topics:**
- Variables: `const`, `let` (no `var`)
- Data types: strings, numbers, booleans, arrays, objects
- Functions: regular, arrow functions `() => {}`
- DOM manipulation:
  - `document.getElementById()` — *used throughout your script*
  - `element.innerHTML`, `.textContent`, `.value`
  - `element.classList.add()`, `.remove()`, `.replace()`
- Event listeners: `addEventListener('click', ...)`, `'input'` event
- Template literals: `` `Hello ${name}` ``

**🔨 Mini-Project:** Build a "character counter" tool: a text area where typing updates a live character/word count below it using DOM manipulation and event listeners.

**📚 Resources:**
- [JavaScript.info](https://javascript.info/) — Part 1 (Chapters 1–5) & Part 2 (Document chapter)
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [Eloquent JavaScript](https://eloquentjavascript.net/) — Chapters 1–4, 14–15 (free online)

---

### Week 6: JavaScript Intermediate — Async, APIs, Storage

**Topics:**
- `async/await` and Promises — *your `performConversion()` uses this*
- `fetch()` API — *your app sends POST requests to `/convert`*
  - Setting headers: `'Content-Type': 'application/json'`
  - `JSON.stringify()` and `response.json()`
  - Error handling with `try/catch`
- `setTimeout` and `clearTimeout` — *your debounce logic*
- Debounce pattern — *used in auto-convert*
- `localStorage` — *your theme preference storage*
- `window.matchMedia()` — *detecting system dark mode*
- Clipboard API: `navigator.clipboard.write()`, `navigator.clipboard.readText()` — *your copy/paste*
- `ClipboardItem`, `Blob` — *your rich text copy*
- Fallback patterns: `document.execCommand('copy')` — *your HTTP fallback*

**🔨 Mini-Project:** Build a "Translation Box" that takes text input, sends it to a free API (like LibreTranslate), displays the result, has auto-translate with debounce, and saves the preferred language in `localStorage`.

**📚 Resources:**
- [JavaScript.info — Async](https://javascript.info/async)
- [MDN Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
- [MDN Clipboard API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API)
- [MDN localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)

---

### Week 7: Flask — Web Framework

**Topics:**
- Installing Flask in a virtual environment (`venv`)
- `requirements.txt` and `pip freeze`
- App factory: `app = Flask(__name__)`
- Routing: `@app.route('/')`, `@app.route('/convert', methods=['POST'])`
- Template rendering: `render_template('index.html')`
- Jinja2 template basics: `{{ url_for('static', filename='...') }}`
- Handling JSON: `request.get_json()`, `jsonify()`
- HTTP methods: GET vs POST
- Error responses: `return jsonify({'error': '...'}), 400`
- `app.run(host='0.0.0.0', port=5000, debug=True)`
- Project structure: `templates/`, `static/css/`, `converter/`
- Static files serving

**🔨 Mini-Project:** Build a "Unit Converter" Flask app with:
- A homepage with an input form
- A `/convert` POST API endpoint
- Conversion logic in a separate Python package
- Results displayed dynamically via `fetch()` + JavaScript

**📚 Resources:**
- [Flask Official Tutorial](https://flask.palletsprojects.com/en/latest/tutorial/)
- [Flask Quickstart](https://flask.palletsprojects.com/en/latest/quickstart/)
- [Miguel Grinberg's Flask Mega-Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world) (free)
- [Real Python — Flask Tutorial](https://realpython.com/python-web-applications-with-flask-part-i/)

---

### Week 8: Unicode & Bengali Text Processing

**Topics:**
- What is Unicode? UTF-8 vs UTF-16 vs ASCII
- Unicode code points: `\u0980` to `\u09FF` (Bengali block)
- Python `ord()` and `chr()` functions
- Character classification: vowels (স্বরবর্ণ), consonants (ব্যঞ্জনবর্ণ), kars (কার), halant (হসন্ত)
- String manipulation at character level: iterating over Unicode strings
- Multi-byte string handling (your `util.py` functions)
- Character mapping with dictionaries — *your `keymap.py`*
- The Bijoy encoding system — how it maps Unicode to ASCII art
- Conjunct consonants (যুক্তাক্ষর) and how they decompose
- Pre-kar vs post-kar reordering logic — *core of your `engine.py`*
- `re` module for pattern replacement in Unicode text

**🔨 Mini-Project:** Build a Bengali text analyzer that:
- Takes Bengali Unicode text as input
- Counts vowels, consonants, kars, and conjuncts separately
- Detects and highlights mixed Bengali/English text
- Implements the `get_chunks()` function from your `app.py` from scratch

**📚 Resources:**
- [Unicode Consortium — Bengali Block](https://unicode.org/charts/PDF/U0980.pdf)
- [Joel Spolsky — The Absolute Minimum Every Developer Must Know About Unicode](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [Python Unicode HOWTO](https://docs.python.org/3/howto/unicode.html)
- [Wikipedia — Bijoy Keyboard](https://en.wikipedia.org/wiki/Bijoy_keyboard)

---

## 🗓️ MONTH 3 — Professional Skills & Full Rebuild (Weeks 9–12)

### Week 9: Git, Version Control & Project Management

**Topics:**
- Git basics: `init`, `add`, `commit`, `status`, `log`, `diff`
- Branching: `branch`, `checkout`, `merge`
- Remote repositories: GitHub, `push`, `pull`, `clone`
- `.gitignore` — ignoring `venv/`, `__pycache__/`, etc.
- Writing good commit messages
- GitHub features: Issues, Pull Requests, README.md
- Markdown syntax for documentation
- Semantic versioning (v1.0.0, v1.1.0, etc.)

**🔨 Mini-Project:** Initialize your BornoType project as a Git repo. Create a proper `.gitignore`, write a professional `README.md` with badges, create feature branches, and push to GitHub.

**📚 Resources:**
- [Git Official Book (Pro Git)](https://git-scm.com/book/en/v2) — Chapters 1–3 (free)
- [GitHub Skills](https://skills.github.com/) — interactive courses
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)

---

### Week 10: Debugging, Testing & DevTools

**Topics:**
- **Browser DevTools:**
  - Elements tab: inspecting/editing HTML & CSS live
  - Console tab: `console.log()`, `console.error()`, `console.table()`
  - Network tab: inspecting `fetch()` requests & responses
  - Application tab: checking `localStorage`
  - Breakpoints and step-through debugging in JS
- **Python Debugging:**
  - `print()` debugging (you already have `debug_output.txt`)
  - `pdb` / `breakpoint()` — Python's built-in debugger
  - Reading tracebacks and stack traces
  - Flask debug mode and auto-reloader
- **Testing:**
  - `unittest` module: writing test cases
  - `pytest` — simpler test framework
  - Testing your converter: input → expected output assertions
  - Testing Flask routes with test client

**🔨 Mini-Project:** Write a test suite for your converter:
- 20+ test cases covering common Bengali words, conjuncts, edge cases
- Test the Flask `/convert` API endpoint
- Set up `pytest` and run tests from command line

**📚 Resources:**
- [Chrome DevTools Docs](https://developer.chrome.com/docs/devtools/)
- [Real Python — Debugging with pdb](https://realpython.com/python-debugging-pdb/)
- [Real Python — pytest](https://realpython.com/pytest-python-testing/)
- [Flask Testing Docs](https://flask.palletsprojects.com/en/latest/testing/)

---

### Week 11: Deployment & Production

**Topics:**
- **Deployment options:**
  - PythonAnywhere (free, easiest for Flask)
  - Railway / Render (free tier)
  - VPS with Nginx + Gunicorn (advanced)
- **Production setup:**
  - WSGI servers: Gunicorn vs development server
  - Environment variables for config
  - `DEBUG = False` in production
  - HTTPS and why Clipboard API needs it
- **Domain & DNS:**
  - Connecting a custom domain
  - DNS records: A, CNAME
- **Performance:**
  - CSS/JS minification
  - Caching static files
  - Gzip compression
- **SEO basics:**
  - Meta tags: `<title>`, `<meta name="description">`
  - Open Graph tags for social sharing
  - `robots.txt` and `sitemap.xml`
- **Google AdSense:**
  - How ad integration works (your `ads-container` div)
  - Ad placement best practices

**🔨 Mini-Project:** Deploy BornoType to PythonAnywhere or Render. Set up a custom domain, add proper meta tags, and configure HTTPS.

**📚 Resources:**
- [PythonAnywhere Flask Guide](https://help.pythonanywhere.com/pages/Flask/)
- [Render Flask Deployment](https://render.com/docs/deploy-flask)
- [Real Python — Deploying Flask](https://realpython.com/flask-by-example-part-1-project-setup/)
- [MDN — SEO Basics](https://developer.mozilla.org/en-US/docs/Glossary/SEO)

---

### Week 12: Full Rebuild + Advanced Features

**Topics:**
- Rebuild the entire BornoType from scratch (no looking at old code!)
- Plan features before coding (write specs first)
- **Advanced features to implement:**
  - File upload: convert `.txt` files in bulk
  - Reverse conversion: Bijoy → Unicode
  - Keyboard shortcut support (Ctrl+V auto-convert)
  - PWA (Progressive Web App) — make it installable
  - History/recent conversions using `localStorage`
  - Character count and word count display
- Code organization best practices
- Writing clean, maintainable code
- Code commenting and documentation

**🔨 Final Project:** Rebuild BornoType v2.0 from an empty folder. Include at least 2 new features that weren't in the original. Write tests. Deploy it. Push to GitHub with a polished README.

**📚 Resources:**
- [12 Factor App](https://12factor.net/) — production app best practices
- [MDN — Progressive Web Apps](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
- [Clean Code concepts for Python](https://github.com/zedr/clean-code-python)

---

## 📖 Complete Resource Library

### Books (Free Online)
| Book | What It Covers |
|---|---|
| [Automate the Boring Stuff](https://automatetheboringstuff.com/) | Python fundamentals |
| [Eloquent JavaScript](https://eloquentjavascript.net/) | JavaScript deep dive |
| [Pro Git](https://git-scm.com/book/en/v2) | Git mastery |
| [Flask Mega-Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world) | Flask from zero to deploy |

### Reference Docs (Bookmark These)
| Resource | URL |
|---|---|
| Python Docs | https://docs.python.org/3/ |
| MDN Web Docs | https://developer.mozilla.org/ |
| Flask Docs | https://flask.palletsprojects.com/ |
| CSS Tricks | https://css-tricks.com/ |
| JavaScript.info | https://javascript.info/ |

### Practice Platforms
| Platform | Best For |
|---|---|
| [HackerRank](https://hackerrank.com/) | Python & JS challenges |
| [freeCodeCamp](https://freecodecamp.org/) | HTML/CSS/JS projects |
| [Frontend Mentor](https://frontendmentor.io/) | Real-world CSS challenges |
| [Exercism](https://exercism.org/) | Python exercises with mentoring |

### YouTube Channels
| Channel | Best For |
|---|---|
| Corey Schafer | Python & Flask |
| Traversy Media | HTML/CSS/JS crash courses |
| The Net Ninja | Flask & JavaScript |
| Fireship | Quick concept explainers |

---

## 📅 Daily Schedule Template

| Time | Activity | Duration |
|---|---|---|
| **Session 1** | Study theory (read/watch) | 45 min |
| **Break** | Rest | 10 min |
| **Session 2** | Code along with tutorials | 45 min |
| **Break** | Rest | 10 min |
| **Session 3** | Work on mini-project | 60 min |
| **Total** | | ~3 hours/day |

> [!IMPORTANT]
> **Consistency beats intensity.** 2–3 focused hours daily is better than 10-hour weekend marathons. If you miss a day, don't try to "catch up" — just continue where you left off.

---

## ✅ Progress Checklist

### Month 1 — Foundations
- [ ] Can write Python classes with methods from scratch
- [ ] Understand packages, imports, and `__init__.py`
- [ ] Can build responsive layouts with Flexbox
- [ ] Can implement dark/light themes with CSS variables
- [ ] Can write CSS animations and transitions

### Month 2 — Core Skills
- [ ] Can manipulate the DOM without any library
- [ ] Can use `fetch()` with async/await to call APIs
- [ ] Can implement debounce, clipboard copy, localStorage
- [ ] Can build a Flask app with routes, templates, and JSON APIs
- [ ] Understand Unicode and can classify Bengali characters

### Month 3 — Professional
- [ ] Can use Git confidently (branch, merge, push)
- [ ] Can debug with browser DevTools and Python pdb
- [ ] Can write and run tests with pytest
- [ ] Can deploy a Flask app to the internet
- [ ] **Can rebuild BornoType from scratch without any help** ✨

---

> [!CAUTION]
> **The #1 mistake learners make:** Watching tutorials without coding. For every 30 minutes of watching/reading, spend at least 60 minutes writing code. Break things. Fix them. That's how you truly learn.
