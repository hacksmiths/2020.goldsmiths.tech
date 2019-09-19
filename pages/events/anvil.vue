<template>
  <div id='event'>
    <EventHero :event='hero' />
    <!-- Content inside of the EventIntroText tags will display on the left-hand side of the intro section, below the hero unit -->
    <EventIntroText :sidebar='introTextSidebarItems'>
      <h2>Build awesome anvils WuW, with all the support you need.</h2>
      <p>You ever seen that looney tunes</p>
      <p>With the coyoti and the bird?</p>
      <!-- <p>Find out more <a href='#'>here</a>.</p> -->
    </EventIntroText>

    <!-- Can comment this out if you do not want to display the supporters section -->
    <EventSupporters :supporters='supporters' :askForSponsorship='askForSponsorship' v-if='supporters.length > 0' />
    <EventFaq :faqs='faqs' />
  </div>
</template>

<script>
import EventHero from '~/components/EventHero';
import EventIntroText from '~/components/EventIntroText';
import EventSupporters from '~/components/EventSupporters';
import EventFaq from '~/components/EventFaq';

export default {
  data() {
    return {
      // This section is for the hero unit content
      // Assets go in /static
      hero: {
        background: '/events/doc/hero.jpg',
        logo: '/events/doc/logo.svg',
        name: 'Anvil Hack V',
        desc: 'Anvil\'s drop. They also can enhance things if you have shiny books.',
        buttons: [
          { label: 'Highlights from 2019', path: '/no-website-yet' },
          { label: 'Get free tickets, if you lost the game', path: '/free-tix' }
        ]
      },

      // This section is for the info blocks on the right-hand side of the intro section, below the hero unit
      introTextSidebarItems: [
        {
          title: 'When',
          content: '19th April 2020'
        },
        {
          title: 'Where',
          // content: 'St James Hatcham Building<br>Goldsmiths, University of London<br>SE14 6AD'
          content: 'I don\'t know tbh'
        },
        {
          title: 'Twitter',
          content: '#AnvilHack'
        }
      ],

      // These are the logos to show as supporters. These must be images in the /static/supporters directory, and must be in .png format. 
      // Leave array empty if you want to hide this section
      supporters: ['goldsmiths', 'doc', 'goldsu', 'github'],
      // If false, the line asking for sponsorship will not show
      askForSponsorship: true,

      // List of FAQs
      faqs: [
        // {
        //   q: `What is a hackathon`,
        //   a: `Hackathons are invention marathons for developers, designers, psychologists, researchers and more. During the event, participants ('hackers') will build projects that answer our challenges to build awesome creative projects.`
        // },
        // {
        //   q: `Who owns the projects?`,
        //   a: `All projects built at this event belongs completely to the teams. However, to generate the widest benefit from this event, we encourage attendees to provide Open Source licenses for the results of their work.`
        // },
        // {
        //   q: 'What should I bring?',
        //   a: 'All participants will need to bring their laptop, charger(s) and any other devices they wish to work on.'
        // },
        // {
        //   q: 'How much does it cost?',
        //   a: `We want to make this event accessible for everyone, so there is no charge to enter. To make this possible, we need sponsorship.`
        // },
        {
          q: `I don't think this is for me.`,
          a: `Anvil's are powerful though.`
        },
        {
          q: `Do I need a team?`,
          a: `You don’t need a team to take part; it’s perfectly acceptable to create a solo project. However, during the event itself, there will be opportunities to share ideas and connect with your fellow hackers to form a team. As organisers, we’ll do our best to encourage and facilitate teamwork across the weekend.`
        }
      ]
    }
  },
  components: {
    EventHero,
    EventIntroText,
    EventSupporters,
    EventFaq
  }
}
</script>