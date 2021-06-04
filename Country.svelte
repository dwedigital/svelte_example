<script>
  import { onMount } from "svelte";
  import { createClient } from "@supabase/supabase-js";

  const supabaseUrl = "https://mghyfhtjwmaupukxoqeo.supabase.co";
  const supabaseKey =
    "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoiYW5vbiIsImlhdCI6MTYxODA1MDU2MSwiZXhwIjoxOTMzNjI2NTYxfQ.ekOSMgAXg57tZOa2GRxXbq3TPvkf__5bBdNdtRb4TrE";
  const supabase = createClient(supabaseUrl, supabaseKey);
  onMount(() => {
    getCountry();
  });
  let countryList = [];
  async function getCountry() {
    let { data: countries, error } = await supabase.from("countries").select("*");
    countryList = countries;
    console.log(countryList);
  }
</script>
<div>
<h2>Testing Supabase Database</h2>
<ul class="mt-5">
{#each countryList as country}
<li>{country.country}</li>
{/each}

</ul>
</div>

