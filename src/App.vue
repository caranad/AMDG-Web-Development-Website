<template>
  <div class = "amdg_header_container">
    <div class = "amdg_header">
      <Header/>
      <Slider v-bind:slides = "slides"/>
    </div>

    <div class = "amdg_blurb_container" id = "about">
      <h1>WHO ARE WE?</h1>
      <p>
        AMDG Web Development was founded in September 2019 with one thing in mind: 
        building applications for clients, businesses and aspiring individuals. 
        After completing his studies in Computer Science at the University of Toronto, 
        our founder embarked on a new journey to restart his development career and 
        provide the best website application services to all walks of life. 
      </p>

      <p>
        Driven by Our Lord's Parable of the Talents (St. Matthew 25:14-30), our founder was inspired
        to use his God-given talents and apply them to the service of others. 
        This can be summarized through the name of our company, "AMDG": the Latin 
        abbreviation for "Ad Majorem Dei Gloriam", or "For the greater glory of God"; 
        which strongly reflects our founder's beliefs in being at the service of others, 
        and giving praise to Him in that manner. 
      </p>

      <div class = "amdg_products_container">
        <h1>WE CREATE...</h1>

        <GridContainer>
          <div class = "grid half" v-for = "product in products" :key = "product.title">
            <Grid 
              v-bind:type = "'text'" 
              v-bind:title = "product.title" 
              v-bind:content = "product.content" 
              v-bind:imageUrl = "product.imageUrl"
            />
          </div>
        </GridContainer>
      </div>
    </div>

    <div class = "amdg_technologies_container lightgray">
      <h1>OUR TECHNOLOGIES</h1>

      <GridContainer>
        <div class = "grid quarter" v-for = "tech in technologies" :key = "tech.language">
          <Grid 
            v-bind:type = "'text'" 
            v-bind:title = "tech.language" 
            v-bind:imageUrl = "tech.imageUrl"
          />
        </div>
      </GridContainer>
    </div>

    <div class = "amdg_pricing_container darkblue" id = "pricing">
      <h1>PRICING</h1>

      <GridContainer>
        <div class = "grid triple" v-for = "price in pricing" :key = "price.title">
          <Grid 
            v-bind:type = "'list'" 
            v-bind:title = "price.title" 
            v-bind:subtitle = "price.subtitle" 
            v-bind:content = "price.content"
            v-bind:imageUrl = "price.imageUrl"
          />
        </div>
      </GridContainer>
    </div>

    <div class = "amdg_contact_container" id = "contact">
      <h1>WORK WITH US!</h1>

      <h3>
        Interested in working with AMDG Web Development? Contact us at amdg@gmail.com 
        with a description of your project and we'll come up with a quote if we're up to 
        this project!
      </h3>
    </div>

    <div class = "amdg_footer_container">
      <Footer/>
    </div>
  </div>
</template>

<script>
import Slider from './components/Slider'
import Header from './components/Header'
import GridContainer from './components/GridContainer'
import Grid from './components/Grid';
import Footer from './components/Footer';

export default {
  name: 'app',
  components: {
    Slider, Header, GridContainer, Grid, Footer
  },
  data() {
    return {
      slides: [
          {
              "id": 0,
              "text": "AMDG Web Development",
              "subtext": "Developing web applications for the world",
              "style": {
                  "backgroundImage": "url('" + require('./assets/slide_background_1.jpg') + "')",
                  "backgroundRepeat": "no-repeat",
                  "backgroundSize": "100% 100%"
              }
          }
      ],
      products: [
        {
          title: "WORDPRESS WEBSITES",
          content: `
            Since 2016 the founder of AMDG Web Development has developed various websites using his knowledge of the 
            Wordpress framework and the Divi site builder, generating high-quality, visually appealing websites for 
            displaying company info, powering e-commerce shops, and portfolio websites from scratch. Some examples of his work can be
            found in the Portfolio section of his website.
          `,
          imageUrl: require('./assets/wordpress.svg')
        },
        {
          title: "CUSTOMIZED WEB APPLICATIONS",
          content: `
            AMDG Web Development also provides customers with the choice of customized web applications, complete with a 
            REST API backend, fully customizable software functionality, on top of a sleek, beautifully handcrafted front-end 
            to entice users while providing them with an application service that can solve their everyday problems and 
            needs. To see a list of what technologies we use for customized web applications, please see the Technologies section
            of our website.
          `,
          imageUrl: require('./assets/web.svg')
        }
      ],
      technologies: [
        {
          language: "HTML 5",
          imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/1200px-HTML5_logo_and_wordmark.svg.png"
        },
        {
          language: "CSS",
          imageUrl: "https://eternitech.com/wp-content/uploads/2016/11/CSS3.png"
        },
        {
          language: "Javascript",
          imageUrl: "https://seeklogo.com/images/J/javascript-logo-E967E87D74-seeklogo.com.png"
        },
        {
          language: "jQuery",
          imageUrl: "https://i.pinimg.com/originals/c0/26/1a/c0261af0418d8ad72fdd8a7f4379d7db.png"
        },
        {
          language: "MongoDB / Node.js",
          imageUrl: "https://koenig-media.raywenderlich.com/uploads/2014/03/MongoDB.png"
        },
        {
          language: "Express.js",
          imageUrl: "https://cdn-web.studio3t.com/knowledge-base/wp-content/uploads/expressjs-logo.png?x12322"
        },
        {
          language: "Angular / React / Vue",
          imageUrl: "https://miro.medium.com/max/1200/1*yhU3xtt7wXBtGNTJbO8G3Q.png"
        },
        {
          language: "PHP / MySQL",
          imageUrl: "https://www.ktchost.com/blog/wp-content/uploads/2009/08/mysql.png"
        }
      ],
      pricing: [
        {
          title: "SIMPLE WORDPRESS WEBSITE",
          subtitle: "$200",
          content: [
            "Customized theme using the Divi builder",
            "Access to thousands of Wordpress plugins for your Wordpress needs",
            "Great for startups, bloggers and portfolio websites"
          ],
          imageUrl: require('./assets/divi.jpeg')
        },
        {
          title: "E-COMMERCE WORDPRESS WEBSITE",
          subtitle: "$400",
          content: [
            "Customized theme using the Divi builder",
            "Uses Woocommerce to power your online shop",
            "Support for Paypal, credit cards and other online transactions"
          ],
          imageUrl: require('./assets/woo.png')
        },
        {
          title: "CUSTOMIZED WORDPRESS WEBSITE",
          subtitle: "$600",
          content: [
            "Contains customizable website template with its own look and feel",
            "Can be used to perform services other than e-commerce",
            "Access to multiple Wordpress plugins at your service"
          ],
          imageUrl: require('./assets/wordpress_alt.png')
        },
        {
          title: "CUSTOMIZED STATIC WEBSITE",
          subtitle: "$800",
          content: [
            "Contains customizable website template with its own look and feel",
            "Easily customizable and stands out from generic templates",
            "Professionally written website text to attract customers"
          ],
          imageUrl: require('./assets/static_web.png')
        },
        {
          title: "FULL STACK WEB APPLICATION",
          subtitle: "$1000",
          content: [
            "Web application powered using MEAN stack (Mongo, Express, Angular, Node)",
            "REST API backend and access to its statistics",
            "Customizable based on what you want and how you want",
            "Great for large-scale firms, medium-sized businesses that don't want a generic template"
          ],
          imageUrl: require('./assets/web app.png')
        }
      ]
    }
  }
}
</script>

<style>
* {
  font-family: 'Red Hat Display', sans-serif;
}

html, body {
  margin: 0;
  padding: 0;
}

.amdg_header_container {
  text-align: center;
}

.amdg_blurb_container, .amdg_technologies_container, 
.amdg_projects_container, .amdg_contact_container, .amdg_pricing_container {
  padding-left: 25px;
  padding-right: 25px;
  padding-bottom: 25px;
}

.lightgray {
  background-color: #bcb6bb;
}

.darkblue {
  background-color: #232B87;
}

.amdg_pricing_container {
  color: white;
}

.grid {
  margin-bottom: 50px;
}

.grid.half {
  flex: 1 0 50%;
}

.grid.quarter {
  flex: 1 0 25%;
}

.grid.triple {
  flex: 1 0 33%;
}

</style>
