<template>
  <div>
    <Home />
    <About />
    <Brand />
    <Footer />
  </div>
</template>
<script>
import Home from '@/components/Home/Home';
import About from "@/components/Home/About";
import Brand from '@/components/Home/Brand';
import Footer from '@/components/Home/Footer'
export default {
  name: 'HomePage',
  components: {
    Home,
    About,
    Brand,
    Footer
  }
}
</script>