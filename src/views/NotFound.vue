<script>
import { defineComponent } from 'vue'; // Import the defineComponent function
import { useRouter } from 'vue-router'; // Import the useRouter function

export default defineComponent({
  setup() {
    const router = useRouter(); // Use the useRouter function to access the router instance

    // Return the template as a string or template literal
    return `
      <div>
        <h1>Not Found</h1>
        <p>
          Oops, we couldn't find that page. Try going
          <router-link to="/">home</router-link>
        </p>
      </div>
    `;
  }
});
</script>
