// org chart: https://jscharting.com/examples/chart-types/organizational/alphabet/#
// area step: https://jscharting.com/examples/chart-types/area/step/#
<style>
.organizationDown {
	height: 400px;
}
</style>

<template>
	<JSCharting :options="options" class="organizationDown"></JSCharting>
</template>

<script>
import JSCharting from 'jscharting-vue';

export default {
  data() {
    return {
      name: 'organizationDown',
      options: {
        debug: true,
        defaultPoint: {
          label: {
            text: '<b>%name</b><br/>%adm',
            autoWrap: false
          },
          tooltip: '<b>%name</b><br/>%desc'
        },
        type: 'organization down',
        legend_visible: false,
        defaultSeries: {
          line_color: 'black',
          line_width: 1,
          palette: 'warmEarth',
          defaultPoint_annotation: {
            padding: 5,
            corners: [
              'round',
              'square',
              'round',
              'square'
            ],
            margin: [15, 5, 10, 0]
          }
        },
        series: [{
          points: [{
              name: 'Alphabet',
              id: 'a',
              attributes: {
                type: 'root',
                desc: '',
                adm: 'Larry Page, Sergey Brin, Eric Schmidt',
                from: 2015
              }
            },
            {
              name: 'Calico',
              id: 'c',
              parent: 'a',
              attributes: {
                type: 'company',
                desc: 'Research into longevity, life expansion.',
                adm: 'Arthur Levinson',
                from: 2013
              }
            },
            {
              name: 'Google X',
              id: 'x',
              parent: 'a',
              attributes: {
                type: 'company',
                desc: 'Self-driving cars, delivery drones and other projects',
                adm: 'Astro Teller',
                from: 2010
              }
            },
            {
              name: 'Google Capital',
              id: 'gc',
              parent: 'a',
              attributes: {
                type: 'company',
                desc: 'Investments',
                adm: 'David Lawee',
                from: 2013
              }
            },
            {
              name: 'Google',
              id: 'g',
              parent: 'a',
              attributes: {
                type: 'company',
                desc: 'All traditional products of Google',
                adm: 'Sundar Pichai',
                from: 1998
              }
            },
            {
              name: 'Nest',
              id: 'n',
              parent: 'a',
              attributes: {
                type: 'company',
                desc: 'Thermostats and smart-home devices',
                adm: 'Tony Fadell',
                from: 2010
              }
            },
            {
              name: 'YouTube',
              id: 'y',
              parent: 'g',
              attributes: {
                type: 'product',
                desc: 'The video-hosting service',
                adm: '',
                from: 2005
              }
            },
            {
              name: 'Google Search',
              id: 'gs',
              parent: 'g',
              attributes: {
                type: 'product',
                desc: 'The original, core Google search engine',
                adm: '',
                from: 1997
              }
            },
            {
              name: 'Google AdSense',
              id: 'ga',
              parent: 'g',
              attributes: {
                type: 'product',
                desc: 'Online advertising',
                adm: '',
                from: 2003
              }
            },
            {
              name: 'Google DeepMind',
              id: 'dm',
              parent: 'g',
              attributes: {
                type: 'product',
                desc: 'Artificial intelligence research',
                adm: '',
                from: 2010
              }
            }
          ]
        }]
      },
    }
  },
      components: {
        JSCharting
      }
};
</script>
