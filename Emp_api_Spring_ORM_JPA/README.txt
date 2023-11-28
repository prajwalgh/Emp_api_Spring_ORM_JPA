----------------Coupling--------------

	It is very common in software development in java one layer make use of another layer.
	While doing that the layer which using another layer is know as dependent .
	The layer which is getting using is called as dependency.
	If dependency needs to be change that affect dependent it leads to a common software problem known as tight coupling.
	Tight Coupling is bad and must be avoided.
	In traditional approach dependent was responsible for object creation of all of its dependencies which leads to tight coupling.
	Exact reverse approach of this is dependent is no more responsible for object creation of it dependencies insted 
	some external mechanism will create both the object's and pass dependency to its dependent.
	This is know as "Dependency Injection". 
	Spring gives you dependency injection .
	In other words two layers must be loosely coupled with each other.
	In order to do this on layer must only be aware of and communicate with other layer using interfaces.
	In implementation this is know as " Coding To Interfaces".
	
	This is the exact reason why spring framework was written the core principle of spring frame is to avoid this tight coupling among layer.
	In order to achieve loose coupling we use spring framework.
	
	spring does following thing 
							A) Spring takes the responsibility of creating object of dependency and dependent both.
									-It is done by an spring object known as spring container.
									-Spring container is also known as IoC container(Inversion of control)
									-This object been called as "Beans".
									-Root tag of xml is Beans 
									-One Beans tage has multipe bean tag
									-Every bean in the spring container has unique Id associated with it.
									hence spring container is also known as " Bean Container".
							B) Spring container object can be configured by couple of 
									1. XML : this is traditional  and old way to configure spring container. it is steel valid and supported by spring. 
										but it is not used these days.
										-Writing xml is all together is a totally different syntax  as xml is different language.
										-Writing xml name spaces is not only difficult but also error prone.
										-Values in the xml attribute are written in "" . hence if there are any typing errors they wont be caought until run time.
										-Hence it becomes difficult for java developer to write xml configuration file.
										-To exactly avoid all this problem second way is evolved that is Annotation contfiguration.m
									2. Annotation : This is new , popular and common approach this is the most common approach in todays time.
										-was adder in sprint 2.5 and above
										step to use annotation:
											1) annotate classes using stereo type annotation to register class as spring bean.
											following are stereo type annotation.
												a) @Compoinet : this is a generic annotation use to mark any class as spring bean.
												b) @Repository : this is return on top of DAO Classes.
															Hence Dao class is also called as repository classes.
												c) @Service : this is written on top of service classes.
												d) @Controler: this is written on top of Controller Classes. 
										above annotation are equivalent of  bean tag in the xml.
										all above annotation are disabled be default in order to enable them we have to use following steps:
											a) right following tag to enable these annotation
												<context:component-scan	base-package="in.co.vwits"><context:component-scan>
												above tag tell spring container to search classes mark with stereo type annotation .
												in the package mentioned or in all of its sub package.
												Best practice is to mention project based package name	.
											b) TO USE ABOVE TAG we have to add necessary name space (context name space).
												Dealing with xml and xml name space is not only difficult but alos error prone task,
												hence new approach is evolved know as java configuration (zero xml)	
												Step 1: To write a configuration class.
												Step 2: Annotate this class with @Configuration .
												Step 3: Annotate the class with @ComponnetScan .
												Step 4: Instancate spring container using AnnotationConfigApplicationContext
										@Autowire is used to do auto wiring which can be use on top  field
	STEPS TO USE SPRING:
		1. Add appropriate dependencies.
		2. Create XML Configuration (applicationContext.xml)
		Note : Name of the xml file can be anything you like but application context is recommended name and used by developer community.
		3. Create Spring Container Object (Differs based on how are we configuring spring container object).
		4. Write appropriate configuration in applicationContext.xml . 
		5. 
		
	Types of Dependency Injection:
		1. Constructor Injection : 
					 <constructor-arg ref="studentDao" ></constructor-arg>
			
		2. Setter Injection/ property injection :
					 <property name="dao" ref="studentDao"></property>
					 
					 
	list of important annotation
		@Component
		@Service
		@Repository
		@Autowire
		@Configuration
		@CompoinentScan
		@Controler
			