
<script>
    export let callThanks;
    import {fullName} from './Store.js';
    import { cardNumber } from './Store.js';
    import {expirationDate} from './Store.js';
    let cvv = '';
    let isValid;
    let expirationDateErr = '';
    let fullNameErr = '';
    let cardNumberErr;
  
    const validateForm = () => {
      expirationDateErr = '';
      fullNameErr = '';
       
  
      isValid = fullName && cardNumber && expirationDate && cvv;
  
      handleExpirationDateInput();
      fullNames();
      cardNumbers();
  
      // Валидация даты
      if ($expirationDate.length > 5) {
        expirationDateErr = '00/00 cannot be blank';
      } else if ($expirationDate.length < 5) {
        expirationDateErr = "Can’t be blank";
      }
    };
  
    const handleExpirationDateInput = () => {
      $expirationDate = $expirationDate.replace(/\D/g, '').replace(/(\d{2})(\d{0,4})/, '$1/$2');
    };
  
    const fullNames = () => {
      fullNameErr = '';
      if (/\d/.test($fullName)) {
        fullNameErr = 'Accepts only letters';
      }
    };
  
    const cardNumbers = () => {
      $cardNumber.replace(/\D/g, '').replace(/(\d{4})(?=\d)/g, '$1 ');
      if ($cardNumber.length< 16) {
        cardNumberErr = 'less than 16 digits';
      }
      else if ($cardNumber.length > 16) {
        cardNumberErr = 'more than 16 digit';
      }else{
        cardNumberErr=''
      }
    };
  
    const submitForm = () => {
      validateForm();
  
      if (isValid && !expirationDateErr && !fullNameErr && !cardNumberErr) {
      
        callThanks();
       
      }
    };
  </script>
  
  <form on:submit|preventDefault={submitForm} class="formVal">
    <label for="fullName">Full Name:</label>
    <input type="text" class="fullName" bind:value={$fullName} on:input={fullNames} />
    {#if fullNameErr}
      <p class="error1">{fullNameErr}</p>
    {/if}
    <br>
  
    <label for="cardNumber">Card Number:</label>
    <input  class="cardNumber" bind:value={$cardNumber} on:input={cardNumbers} />
    {#if cardNumberErr}
      <p class="error1">{cardNumberErr}</p>
    {/if}
    <br>
  
    <label for="expirationDate">Expiration Date:</label>
    <input class="expirationDate" bind:value={$expirationDate} on:input={handleExpirationDateInput} />
    {#if expirationDateErr}
      <p class="error1">{expirationDateErr}</p>
    {/if}
    <br>
  
    <label for="cvv">CVV:</label>
    <input type="" class="cvv" bind:value={cvv} />
    <br>
  
    <button type="submit">Submit</button>
  </form>
  

















  
  <style>
   .formVal{
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 6rem;
   }
    input{
        width: 23.8125rem;
height: 2.8125rem;
flex-shrink: 0;
border-radius: 0.5rem;
border: 1px solid var(--Gradient, #6348FE);

background: var(--White, #FFF);
color: var(--Deep-Violet, #21092F);
font-feature-settings: 'clig' off, 'liga' off;

/* Heading (L) */
font-family: Space Grotesk;
font-size: 1.125rem;
font-style: normal;
font-weight: 500;
line-height: normal;
    }
    label{
        color: var(--Deep-Violet, #21092F);
font-feature-settings: 'clig' off, 'liga' off;

/* Body (M) */
font-family: Space Grotesk;
font-size: 0.75rem;
font-style: normal;
font-weight: 500;
line-height: normal;
letter-spacing: 0.125rem;
text-transform: uppercase;
    }

  </style>
  