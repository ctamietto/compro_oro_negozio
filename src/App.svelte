<script>

  // fonts

  import "@fontsource/roboto/100-italic.css"; 
  import "@fontsource/roboto/300-italic.css"; 
  import "@fontsource/roboto/400-italic.css"; 
  import "@fontsource/roboto/500-italic.css"; 
  import "@fontsource/roboto/700-italic.css"; 
  import "@fontsource/roboto/900-italic.css"; 

  import "@fontsource/roboto-mono/100-italic.css";
  import "@fontsource/roboto-mono/200-italic.css";
  import "@fontsource/roboto-mono/300-italic.css";
  import "@fontsource/roboto-mono/400-italic.css";
  import "@fontsource/roboto-mono/500-italic.css";
  import "@fontsource/roboto-mono/600-italic.css";
  import "@fontsource/roboto-mono/700-italic.css";


  //import Button, { Label } from '@smui/button';
  import Textfield from '@smui/textfield';
  import Icon from '@smui/textfield/icon';
  import HelperText from '@smui/textfield/helper-text';
  import Radio from '@smui/radio';
  import FormField from '@smui/form-field';
  import Select, { Option } from '@smui/select';

  // dati anagrafici
  let nome = '';
  let cognome = '';
  let sesso = '';
  let data_nascita = '';
  let luogo_di_nascita = '';
  let codice_fiscale = '';
  let nazionalita = '';

  // dati residenza
  let residenza_tipo_indirizzo = '';
  let residenza_indirizzo = '';
  let residenza_localita = '';
  let residenza_provincia = '';
  let residenza_cap = '';

</script>

<!--
<Button on:click={() => clicked++} variant="raised">
  <Label>Raised</Label>
</Button>
<Button on:click={() => clicked++} variant="unelevated">
  <Label>Unelevated</Label>
</Button>
<Button on:click={() => clicked++} variant="outlined">
  <Label>Outlined</Label>
</Button>
<Button color="secondary" on:click={() => clicked++} variant="raised">
  <Label>Raised</Label>
</Button>
<Button color="secondary" on:click={() => clicked++} variant="unelevated">
  <Label>Unelevated</Label>
</Button>
<Button color="secondary" on:click={() => clicked++} variant="outlined">
  <Label>Outlined</Label>
</Button>
-->
<div class="page_bar">
    <h1>Anagrafica Cliente</h1>
</div>
<fieldset>
  <legend>Dati Anagrafici</legend>
  <div class="sezione_dati">
    <div>
      <Textfield variant="outlined" bind:value={nome} label="Nome">
      </Textfield>
    </div>
    <div>
      <Textfield variant="outlined" bind:value={cognome} label="Cognome">
      </Textfield>
    </div>
    <div>
      <Select bind:value={sesso} label="Sesso">
        {#each ['M', 'F'] as item_sesso}
          <Option value={item_sesso}>{item_sesso}</Option>
        {/each}
      </Select>  
    </div>    
    <div>
      <Textfield variant="outlined" bind:value={data_nascita} type="date" label="Data di Nascita">
      </Textfield>
    </div>
    <div>
      <Textfield variant="outlined" bind:value={luogo_di_nascita} label="Luogo di Nascita">
      </Textfield>
    </div>
    <div>
      <Textfield variant="outlined" bind:value={codice_fiscale} label="Codice Fiscale">
      </Textfield>
    </div>
    <div>
      <Textfield variant="outlined" bind:value={nazionalita} label="Nazionalità">
      </Textfield>
    </div>
  </div>
</fieldset>
<fieldset>
  <legend>Residenza</legend>
  <div class="sezione_dati">
    <div>
      <Select bind:value={residenza_tipo_indirizzo} label="Tipologia">
        {#each ['Via', 'Strada' , 'Corso' , 'Piazza'] as item_rtp}
          <Option value={item_rtp}>{item_rtp}</Option>
        {/each}
      </Select>  
    </div>    
    <div>
      <Textfield variant="outlined" bind:value={residenza_indirizzo} label="Indirizzo" input$class="indirizzo" >
      </Textfield>
    </div>    
    <div>
      <Textfield variant="outlined" bind:value={residenza_localita} label="Località">
      </Textfield>
    </div>    
    <div>
      <Textfield variant="outlined" bind:value={residenza_provincia} label="Provincia" input$class="provincia" >
      </Textfield>
    </div>    
    <div>
      <Textfield variant="outlined" bind:value={residenza_cap} label="CAP" input$class="cap">
      </Textfield>
    </div>    
  </div>
</fieldset>
<style>
  .sezione_dati {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    gap: 10px;
  }
  fieldset {
    border-width:1px;
  }
  legend {
    font-style: italic;
    color:var(--mdc-theme-primary, #ff3e00);
  }
  h1 {
    margin:8px;
  }
  .page_bar {
    background-color:var(--mdc-theme-primary, #ff3e00);
    border: 2px solid #ff3e00;
    border-radius: 5px;
    color: white;
    font-style: italic;
    margin: 0px;
    padding: 0px;
    margin-bottom: 10px;
  }
  :global(.indirizzo) {
    width: 400px;
  }
  :global(.provincia) {
    width: 60px;
  }
  :global(.cap) {
    width: 50px;
  }
</style>

