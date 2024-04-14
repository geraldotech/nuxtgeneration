<template>
  <div>
    <NuxtLayout>
      <h5>App file</h5>
      <!-- components -->
      <Header/>
      <Profile/>
      <ProfileHeader/>
        <!-- components -->
      <header class="menu">
        <ul>
          <li>
            <NuxtLink to="/">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/blog">Blog</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/events">Events</NuxtLink>
          </li>
        </ul>
      </header>

      <NuxtPage/>
      <Footer/>
    </NuxtLayout>
   <!-- <NuxtWelcome />-->
  </div>
</template>
