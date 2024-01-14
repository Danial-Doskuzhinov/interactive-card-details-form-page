 <script>
     import {cardNumber}  from './Store.js';
     import {expirationDate}  from './Store.js';
     import {fullName}  from './Store.js';
</script>
<div class="card">
   <div>
 <p class="card-number" >{$cardNumber}  </p>
</div>
<div class="card-footer">
 <p class="card-fullName">{$fullName}</p>
 <p class="card-date">{$expirationDate}</p>
</div>
</div> 

<style>
    .card{
        width: 27.9375rem;
height: 15.3125rem;
flex-shrink: 0;
border-radius: 0.625rem;
background: linear-gradient(164deg, #6348FE 4.74%, #610595 88.83%)
    }
    .card-footer{
        display: flex;
        justify-content: space-between;
    }
    .card-fullName{
        color: var(--White, #FFF);
font-feature-settings: 'clig' off, 'liga' off;

/* Body (L) */
font-family: Space Grotesk;
font-size: 0.875rem;
font-style: normal;
letter-spacing: 0.125rem;
text-transform: uppercase;
margin-left: 2rem;

    }
    .card-number{
        margin-left: 2rem;
        padding-top: 8.69rem;
        color: var(--White, #FFF);
font-feature-settings: 'clig' off, 'liga' off;

/* Heading (XL) */
font-family: Space Grotesk;
font-size: 1.75rem;
font-style: normal;
letter-spacing: 0.21388rem;
    }
    .card-date{
        margin-right: 2rem;
        color: var(--White, #FFF);
text-align: right;
font-feature-settings: 'clig' off, 'liga' off;

/* Body (L) */
font-family: Space Grotesk;
font-size: 0.875rem;
font-style: normal;
letter-spacing: 0.125rem;
text-transform: uppercase;
    }
</style>