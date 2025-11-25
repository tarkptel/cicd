<h1>Simple Python CI Pipeline using GitHub Actions</h1>

<p>
  This repository demonstrates a <strong>simple CI pipeline</strong> that runs automated tests on every 
  push or pull request using <strong>GitHub Actions</strong>.  
  If the tests pass, the code can be safely merged into the <code>main</code> branch.  
  If tests fail, merging is blocked.
</p>

<h2>📌 Pipeline Features</h2>
<ul>
  <li>Automatically runs tests on each push and pull request.</li>
  <li>Ensures only tested and verified code enters the <code>main</code> branch.</li>
  <li>Prevents buggy code from being merged.</li>
  <li>Lightweight CI setup — perfect for beginners.</li>
</ul>

<h2>📁 Repository Structure</h2>
<pre>
.
├── app.py               # Simple Python test file / example code
├── test_app.py          # Unit tests (pytest)
└── .github/
    └── workflows/
        └── python-ci.yml   # GitHub Actions workflow for CI
</pre>

<h2>⚙️ GitHub Actions Workflow</h2>
<p>The <code>python-ci.yml</code> workflow performs the following steps:</p>
<ol>
  <li>Checkout the repository code</li>
  <li>Set up Python</li>
  <li>Install required dependencies</li>
  <li>Run tests using <code>pytest</code></li>
</ol>

<h3>🔧 Example Workflow (from this repository)</h3>
<pre>
name: Python CI

on:
  push:
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest

  steps:
  - name: Checkout code
    uses: actions/checkout@v3

  - name: Set up Python
    uses: actions/setup-python@v4
    with:
      python-version: "3.10"

  - name: Install dependencies
    run: |
      pip install pytest

  - name: Run tests
    run: pytest
</pre>

<h2>🧪 Running Tests Locally</h2>
<pre>
pip install pytest
pytest
</pre>

<h2>🔐 Branch Protection</h2>
<p>
  The <code>main</code> branch is protected.  
  GitHub only allows merging when:
</p>
<ul>
  <li>All tests pass</li>
  <li>No workflow errors</li>
</ul>

<h2>🚀 Purpose of This Project</h2>
<p>
  This repository serves as a learning example for:
</p>
<ul>
  <li>Understanding CI (Continuous Integration)</li>
  <li>Using GitHub Actions</li>
  <li>Enforcing code quality through automated tests</li>
  <li>Working with protected branches</li>
</ul>

<h2>👤 Author</h2>
<p>
  <strong>Tark Patel</strong>  
  <a href="https://github.com/tarkptel">GitHub Profile</a>
</p>
