<template>
  <form>
    <div id="page">
      <div>
        <label for="email">Your Email Adress *</label>
        <input type="text" name="email" id="email" autocomplete="email" 
          class="w-full rounded-md border-0 py-2 px-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300" 
        />
      </div>
      <div>
        <label for="email">Retype Your Email Adress *</label>
        <input type="text" name="email" id="email" autocomplete="email" 
          class="w-full rounded-md border-0 py-2 px-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300" 
        />
      </div>
      <div>
        <label for="message">Message *</label>
        <textarea id="message" name="message" rows="3" 
          class="w-full rounded-md border-0 py-2 px-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300"
        />
      </div>
      <button type="submit" 
        class="rounded-md bg-green-500 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-green-600">
        SEND
      </button>
    </div>
  </form>
</template>
