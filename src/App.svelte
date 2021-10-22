<main>
  <h1>Notion Bookmarker</h1>
  <form on:submit|preventDefault={submit}>
    <div>
      <TextField type="text" bind:value={url} label="URL" />
    </div>
    <div>
      <Select bind:value={selectedProject} label="Project">
        {#each projects as project}
          <Option value={project}>{project}</Option>
        {/each}
      </Select>
    </div>
    <div>
      <Select bind:value={selectedCategory} label="Category">
        {#each categories as category}
          <Option value={category}>{category}</Option>
        {/each}
      </Select>
    </div>
    <Button>Submit</Button>
  </form>
</main>

<script lang="ts">
  import TextField from '@smui/TextField'
  import Select, {Option} from '@smui/select'
  import Button from '@smui/button'

  let url = null
  let projects = ["Project 1", "Project 2", "Project 3"]
  let selectedProject: string | null = null
  let categories = ["Category 1", "Category 2", "Category 3"]
  let selectedCategory: string | null = null


  function submit() {
    console.log({url,selectedCategory,selectedProject})
  }
</script>

<style lang="scss">
  form > div {
    margin-bottom: 25px;
  }

  main {
    width: 500px;
    padding: 15px;
    text-align: center;
  }

  h1 {
    font-family: "Roboto";
  }
</style>