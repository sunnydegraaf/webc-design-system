<style>        .grid {
    display: grid;
    grid-template-columns: repeat(var(--cols), 1fr);
    gap: var(--gutter);
}

.grid .col {
    border: 1px solid #000;
    text-align: center;
}

.grid .col[data-cols="2"] {
    grid-column: span 2;
}

.grid .col[data-cols="3"] {
    grid-column: span 3;
}

.grid .col[data-rows="2"] {
    grid-row: 1 / span 2;
}

.grid .col[data-rows="3"] {
    grid-row: 1 / span 3;
}

/* flex */
.flex {
    display: flex;
    width: 100%;
    gap: var(--gutter);
}

.flex div {
    width: 100%;
    border: 1px solid #000;
}

/* x axis only */
[data-align*="center"] {
    display:flex;
    justify-content: center;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
}
/* x + y axis */
[data-align="center center"] {
    align-content: center;
    align-items: center;
}

[data-margin*="top"] {
    margin-top: calc(var(--gutter) * 2);
}

[data-margin*="bottom"] {
    margin-bottom: calc(var(--gutter) * 2);
}

[data-gutter="0"] {
    gap: 0;
}</style>