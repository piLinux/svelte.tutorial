<script>
    export let userName;
    export let jobTitle;
    export let userImage;
    export let description;
</script>

<style>
  .contact-card {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    max-width: 30rem;
    border-radius: 5px;
    margin: 1rem 0;
  }

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 7rem;
  }

  .thumb {
    width: 33%;
    height: 100%;
  }

  .thumb-placeholder {
    background-color: #ddbbab;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .user-data {
    width: 67%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-left: 1rem;
  }

  h1 {
    font-size: 1.25rem;
    font-family: "Roboto Slab", sans-serif;
    margin: 0.5rem 0;
  }

  h2 {
    font-size: 1rem;
    font-weight: normal;
    color: #5a5a5a;
    margin: 0;
    margin-bottom: 0.5rem;
  }

  .description {
    border-top: 1px solid #ccc;
    padding: 1rem;
  }
</style>

<div class="contact-card">
  <header>
    <!-- dynamic CSS class -->
    <div class="thumb" class:thumb-placeholder="{!userImage}">
      <img src="{userImage}" alt="{userName}" onerror="this.src='https://cdn.pilinux.workers.dev/images/GoREST/logo/GoREST-Logo.png'" />
    </div>
    <div class="user-data">
      <h1>{userName}</h1>
      <h2>{jobTitle}</h2>
    </div>
  </header>
  <div class="description">
    <p>{description}</p>
  </div>
</div>
