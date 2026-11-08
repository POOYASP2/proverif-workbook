# ProVerif Workbook

Fill-in-the-blank practice for the ProVerif typed pi-calculus, following the
"Security Verification and Testing" course (slides, Lab 2, past exams).

## Publish on GitHub Pages

1. Create a new public repository, e.g. `proverif-workbook`.
2. Upload `index.html` (and this README) to the root of the `main` branch.
3. Go to **Settings → Pages**, set **Source** to "Deploy from a branch",
   pick `main` and `/ (root)`, then save.
4. After a minute the site is live at
   `https://<your-username>.github.io/proverif-workbook/`.

Progress and drafts are saved in your browser (localStorage).

## Add your own exercises

All content is in the `MODULES` array at the top of the `<script>` in
`index.html`. Five exercise types:

```js
// fill in the blanks: {{id}} marks a slot, blanks lists accepted answers
{type:"fill", title:"...", prompt:"...",
 code:`{{a}} key.`, blanks:{a:["type"]}, hint:"...", explain:"..."}

// multiple choice (multi:true for several correct answers)
{type:"mc", title:"...", question:"...", options:["A","B"], correct:[1], explain:"..."}

// drag and drop: tokens include distractors; mode:"prose" for matching
{type:"drag", title:"...", template:`{{a}} key.`, slots:{a:"type"}, tokens:["type","fun"]}

// ordering: lines in the correct order; [text, rank] lets equal ranks swap
{type:"order", title:"...", lines:["first line","second line"]}

// free writing with a checklist and model answer
{type:"write", title:"...", prompt:"...", starter:"...",
 checks:[["label","snippet that must appear"]], solution:`...`}
```

Answers are compared ignoring whitespace, so `sign(k, sk(kpA))` and
`sign(k,sk(kpA))` are both accepted.
