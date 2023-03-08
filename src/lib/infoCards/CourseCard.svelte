<script>
  // import genericCard.svelte
  import GenericCard from '../GenericCard.svelte';
  import { courses } from '$lib/data/courses.json';
  console.log(courses);
  // filter only courses that course.status is 'Completed'
  const completedCourses = courses.filter(
    (course) => course.status === 'Completed'
  );
  console.log(completedCourses);
</script>

<GenericCard>
  <div class="layout">
    <h3>Courses</h3>
    <ul>
      {#each completedCourses as course}
        <li>
          {course.title}
          ({course.institution})
        </li>
      {/each}
      <div />
    </ul>
    <div class="flex-Text">
      <a href={`./courses`} class="link" style="font-size:15px">+</a>
    </div>
  </div>
</GenericCard>

<style>
  .layout {
    display: grid;
    grid-template-rows: 45px 150px 35px;
  }
  ul {
    list-style: none;
    font-size: 10px;
  }
  li {
    padding: 0.05rem 0;
  }
  .flex-Text {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    gap: 0.8rem;
    padding-top: 0.5rem;
    font-size: 20px;
    height: 32px;
  }
  .link {
    /* background-color: #dddddd; */
    padding: 0.6rem 0.5rem;
    line-height: 2px;
  }

  a {
    color: black;
    font-family: sans-serif;
    text-decoration: none;
    font-size: 0.7rem;
    padding-right: 0.5rem;
    border: 1px solid black;
    border-radius: 0.5rem;
    padding: 2px 10px;
  }
  a:hover {
    color: var(--card-background);
    background: white;
    border: 1px solid white;
  }
</style>
