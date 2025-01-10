<script>
    export let items;
  </script>
  
  <svelte:head>
    <title>Veel Gestelde Vragen</title>
  </svelte:head>
  
  <section id="FAQ" class="faq-section">
    <h1>Veel Gestelde Vragen</h1>
    {#each items[0].componentsCollection.items as item, index}
      <div class="faq-item">
        <details>
          <summary>
            <span class="question-title">{item.title}</span>
          </summary>
          <p>{item.textParagraph}</p>
        </details>
        <div class="underline"></div>
      </div>
    {/each}
  </section>
  
  <style>
    #FAQ {
      background-color: black;
      color: white;
      padding: 2rem;
      margin-top: 100px; 
      height: 100vh;
    }
  
    .faq-item {
      margin-bottom: 1rem;
    }
  
    details {
      background: none;
      border: none;
      padding: 0;
      cursor: pointer;
      list-style: none; /* Removes the default icon */
    }
  
    summary {
      display: flex;
      list-style: none;
    }
  
    summary::after {
  content: '';
  width: 18px;
  height: 10px;
  background: url('arrow.svg');
  background-size: cover;
  margin-left: .75em;
  transition: 0.2s;
}
    .question-title {
      flex-grow: 1;
    }
  
    .faq-item .underline {
      height: 2px;
      background-color: white;
      width: 0%;
      transition: width 0.3s ease;
    }
  
    details.open .underline {
      width: 100%;
    }
  
    p {
      margin: 1rem 0;
      opacity: 0;
      transition: opacity 0.3s ease;
    }
  
    details[open] p {
      opacity: 1;
    }
  
  </style>
  