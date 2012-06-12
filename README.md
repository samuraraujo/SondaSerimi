# Sonda+Serimi

## Introduction

This implementation requires as input a source and target Sparql Endpoint, as well as a class of source instances. 

We decided to redirect the Sonda output to a matcher, which produces correct match between a source instance and a target instance(s). Therefore, the final result of run this command line tool is a link owl:sames between instances.

As a matcher, we used the class-based disambiguation approach presented in [1], also referred to Serimi. 

## Installation 
Serimi was implemented in Ruby. We recommend you install JRuby version of Ruby, using the RVM version manager. 
For more information about RVM, visit:

https://rvm.io/

After install RVM and JRuby, you may need to install one of those gems:

    actionmailer (2.3.2)
	  actionpack (2.3.2)
	  activerecord (2.3.2)
	  activeresource (2.3.2)
	  activesupport (3.1.4, 2.3.2)
	  ai4r (1.11)
	  alexrabarts-term_extraction (0.1.4)
	  amatch (0.2.5)
	  bouncy-castle-java (1.5.0146.1)
	  builder (3.0.0)
	  calais (0.0.11)
	  csvscan (0.1.0)
	  curb (0.7.15)
	  decisiontree (0.3.0)
	  distance_measures (0.0.6)
	  elasticsearch (0.0.0)
	  excelsior (0.1.0)
	  hpricot (0.8.4 java)
	  i18n (0.6.0)
	  jruby-launcher (1.0.8 java, 1.0.7 java)
	  jruby-openssl (0.7.4)
	  json (1.7.3 java, 1.5.3 java, 1.5.1 java)
	  k_means (0.0.7)
	  mime-types (1.16)
	  monster_mash (0.2.3)
	  multi_json (1.3.6)
	  naive_bayes (0.0.3)
	  nokogiri (1.5.0 java)
	  OptionParser (0.5.1)
	  patron (0.4.9)
	  rails (2.3.2)
	  rake (0.9.2, 0.8.7)
	  rest-client (1.6.7)
	  rinruby (2.0.2)
	  ruby-debug-base (0.10.4 java)
	  ruby-debug-ide (0.4.16)
	  sbn (0.9.1)
	  sem_extractor (0.0.4)
	  simplehttp (0.1.3)
	  sources (0.0.1)
	  spruz (0.2.13)
	  term-ansicolor (1.0.7)
	  Text (1.1.2)
	  text (0.2.0)
	  typhoeus (0.2.4)
	  uuidtools (1.0.7)
	  xml-object (0.9.93)
	  xml-simple (1.1.0)
	  yajl-ruby (0.8.2)

We recommend to use the same gem versions than shown above.
 
## Usage

Below, we give an example of use. In this example, we try to find matches for the class SideEffect from Sider dataset on DBPedia dataset.

	ruby sonda.rb -s http://www4.wiwiss.fu-berlin.de/sider/sparql -t http://dbpedia.org/sparql -c http://www4.wiwiss.fu-berlin.de/sider/resource/sider/side_effects 
	
In the current implementation, the target endpoint must be a Virtuoso Openlink Server, because we use specific sparql extension implemented by Virtuoso.
You can modify the queries in the file target.rb to generalize it to any Sparql Engine.



