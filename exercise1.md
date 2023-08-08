## Answer or discuss some of the points below (200-300 words)

Think about a hypothetical situation where we have an application being worked on by a team of about 6 people. The application is in active development and will be released soonLet us assume that the application is coded with some other language than JavaScript/TypeScript, e.g. in Python, Java, or Ruby. You can freely pick the language. This might even be a language you do not know much yourself.

<li> Some common steps in a CI setup include linting, testing, and building. What are the specific tools for taking care of these steps in the ecosystem of the language you picked? You can search for the answers by google.
<li> What alternatives are there to set up the CI besides Jenkins and GitHub Actions? Again, you can ask google!
<li> Would this setup be better in a self-hosted or a cloud-based environment? Why? What information would you need to make that decision?

Answer:

Let's say the language is coded with Ruby. The tools for each step in CI could be:

<li> Linting: RuboCop  https://rubocop.org/#:~:text=RuboCop%20is%20a%20Ruby%20code,tweaked%20via%20various%20configuration%20options.
<li> Testing: We can use minitests on the framework, or Capybara. The former integrates with frameworks such as Ruby on Rails and Sinatra. The latter test the app by simulating how users interact with the application. Another option could be RSpec, which is a Behaviour-Driven Development testing Framework. Cucumber is also a test framework that can be used on Ruby.
<li> Building: As mentioned in the course, Ruby is an interpreted language. It doesn't need a "build" stage for transpile. Instead, it executes instructions directly and freely, without previously compiling a program into machine-language instructions.

The alternatives CI setup are:

<li> AWS CodePipeline: it automates release pipelines and doesn't require a multiple-stage setup. https://aws.amazon.com/codepipeline/
<li> Gitlab CI: Every GitLab user has access to the built-in CI/CD tool GitLab CI. It has a UI, and is cloud-based. If your code is hosted by Gitlab, then this tool is a great choice since it’s easy to use and there is no plugin tools.
<li>GoCD:it is free and open-source. https://www.gocd.org/

When choosing between a self-hosted and a cloud-based CI server. There are several things to consider:

1. The size of your application. If it is a small application, the it is easier to use cloud-based tools. Because this type of tools is easy to setup, and quite many can automates the release pipeline. If you have a large application, perhaps also it involves different teams, then it is better to choose self-hosted server. Self-hosted server can be configured based on your preference flexibly.

2. The customization level of CI configuration. Cloud-based tools are simpler compared to self-hosted tools. If you needs some features that are not supported by the cloud-based server, then self-hosted server is a better option.

3. Build time. If your application takes lots of time in the build stage, and you probably want to allocate more resources to the CI server. In this case, the self-hosted server could be a better choice. On contrast, cloud-based CI server has a limitation in the recources, and it quite often is charged by build time.
