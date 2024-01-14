<!-- Result.svelte -->
<script>
    import Done from '../assets/done.svg';
    import Card from './Card.svelte';
    
</script>
<aside>
    <Card />
  </aside>
<div>
    <img  class="img" src={Done} alt="oke">
    <h2 class="thank"> THANK YOU!</h2>
    <p class="added"> We’ve added your card details</p>
  </div>
 

<style>
    .img{
        margin-left: 43rem;

    }
    .thank{
        color: var(--Deep-Violet, #21092F);
text-align: center;
font-feature-settings: 'clig' off, 'liga' off;

/* Heading (XL) */
font-family: Space Grotesk;
font-size: 1.75rem;
font-style: normal;
font-weight: 500;
line-height: normal;
letter-spacing: 0.21388rem;
    }
    .added{
        color: var(--Purplish-Grey, #8F8694);
text-align: center;
font-feature-settings: 'clig' off, 'liga' off;

/* Heading (L) */
font-family: Space Grotesk;
font-size: 1.125rem;
font-style: normal;
font-weight: 500;
line-height: normal;
    }
</style>
  