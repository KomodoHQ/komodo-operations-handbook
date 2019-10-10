# Investment

_“Find the things that won’t change in your business and invest heavily in those things.”_

_“Take Amazon for example… 10 years from now people aren’t going to say ‘I wish Amazon shipping was slower’ or ‘I wish Amazon had a worse selection’, so we invest heavily in fast shipping and a broad selection.”_

## Where Should We Invest?

With the above in mind (shamelessly [stolen from Basecamp](https://basecamp.com/about)), this document is a discussion around what we should invest in as with regards to the development arm of the company.

1. Faster to deliver functionality.
   - _"I wish Komodo delivered that feature slower."_
2. Less issues, especially that reach the customer.
   - _"I wish Komodo had more bugs in their code that our customers see."_
3. Easier to use.
   - _"I wish it was harder to use what Komodo have created"_
4. Easier to keep running, and understand the current working state.
   - _"I wish it was harder to know when things were working in what Komodo created."_
5. Well documented.
   - _"I wish it was harder to know how this feature Komodo created worked."_
6. Privacy concious.
   - _"I wish more of my customers personal data was publically available because of what Komodo created."_
7. Secure.
   - _"I wish more of my system could be hacked thanks to Komodo."_
8. Performant.
   - _"I wish what Komodo created was slower to use."_
9. Educational.
   - _"I wish less of my team understood how what Komodo created works."_
10. Easier to get help.
   - _"I wish it was harder to get issues resolved with Komodo."_

## Investment Areas

1. What are the biggest barriers to faster delivery? How can we deliver faster?

  - Eliminate interruptions
  - Reduce time to review and amend pull requests
  - Eliminate time waiting for resources / feedback
  - Stop changing tasks and priorities
  - Get rid of slow development environments, jumping through hoops, lack of existing documentation 
  - Understand the problem from the outside
  - Don't reinvent the wheel
  - Stop creating / maintaining overly-complex engineered systems
  - Having to (re)learn systems, especially poorly documented or maintend ones
  - Having to (re)learn tools and technologies, particularly old and slow ones, with poor documentation and inconsistant standards
  - Worries about breaking other parts of the system
  - Scared about breaking production environments, affecting real people
  - Give people space to solve a problem, but give them clear avenues to get immediate support
  - Empower team to take decisions, not have to wait for them

2. How can we reduce the number of issues in our applications? How can we prevent issues from reaching the customer?

  - Make testing and linting mandatory
  - Teach what makes a good test
  - Keep development environments in sync and controlled
  - Reuse well-tested code
  - More people manually testing with more test devices
  - A clear "sign off" process, internally and externally
  - Dont consider testing outside the scope of "finished"
  - Technical discussion groups for knowledge sharing
  - Ensure people are well trained, and follow industry and company standards

3. How can we make our applications easier to use?

  - Understand their intended users
  - Use design patterns they are already familiar with. Don't break expectations
  - Make them very straightforward (limited options)
  - Make them available to more users - accessibility
  - Make them well documented - heres how to do X or Y
  - Make use of user shadowing to observe how users interact with our products, designs and prototypes
  
4. How can we make our applications easier to support? How can we understand and expose the current working state of our applications to customers?

  - Constant, ongoing maintenance with dedicated time just to keep stuff up to date (not features, tweaks etc)
  - Control dependancies and versions
  - Add monitoring tools for dependancies
  - Be aware of and notified of important changes affecting our applications
  - Dedicated support team dealing with errors / bug reports
  - Application and infrastructure monitoring solutions
  - Dont support old systems - stay modern
  - Dedicated support channels
  - Clear bug reports
  - More public betas

5. How can we create and improve upon our documentation? What should be documented?

  - Make some
  - For every feature, have a clear piece of supporting documentation - functional at the least, technical if reasonable
  - Dont consider documentation outside the scope of "finished"
  - Include in PRs
  - Standardise documentation - have templates

6. How can we monitor and control privacy in our applications, and limit the risk of accidental exposure?

  - Challenge ourselves / the customer if this is private information, do we really need it
  - Have a documentated plan for every piece of private information to explain when it will be pruned
  - Ensure there is a way to delete / anonymise private information
  - Silo private data away from application data

7. How can we monitor and improve the security of our applications?

  - Automated Tooling and continous security alerts
  - Make someone else resposible for as much as possible thats outside of code
  - Technical discussion groups for knowledge sharing
  - Security audits
  - Checklists
  - Assess security in PRs

8. How can we monitor and improve the performance of our applications?

  - Understand how they are performing now
  - Have reusable tools to understand their performance and improve on it
  - Leverage performant, lean libraries and code - expel those that are not
  - Dedicated performance and refactoring sprints, measure and improve
  - Set a target for performance, dont allow what's created to exceed it

9. How can we educate our customers?

  - Documentation of features, and decisions
  - Clear "sign off" should include educational content
  - As much "familiar" decisions as possible - and reusable documentation for all

10. How can we better support our customers?

  - Give an estimate for when we will give them an answer to their questions, tell them how much priority we are assigning their issue
  - Give them visability of progress, be transparent
  - Make one person personally responsible for helping solve their problem, take the "apple" approach to support

---

![Just Do It](https://thumbs.gfycat.com/PlasticAdeptAsianpiedstarling-size_restricted.gif)