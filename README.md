RSpec Pairing Exercise
----------------

0) Ensure that your rspec config is set up to show colors and long output using the following the command:

`echo --color -fd >> ~/.rspec`

1) Driver [Dev A]; create a folder (directory) with a name that describes your project.

`mkdir myproject`

2) Driver [Dev A]; Run `rspec`

`rspec`

You should see an error like this:

`cannot load such file -- /Users/sam/Documents/Github/PairProgramming/RSpecExercise/spec (LoadError)`

By running rspec we've checked that we have rspec installed, and this error is because rspec expects a 'spec' folder to exist in the directory we are running it

3) Switch Driver/Navigator Roles

4) Driver [Dev B]; Create a spec folder

`cd myproject`
`mkdir spec`

5) Driver [Dev B]; Run `rspec` 

`rspec`

You should see output like this:

`No examples found.


Finished in 0.00004 seconds
0 examples, 0 failures`

6) Driver [Dev B]; Create an rspec file in that directory

`touch rspec/my_project_spec.rb`

7) Driver [Dev B]; run `rspec` and confirm that the output is unchanged

8) Driver [Dev B]; Start the rspec file with a describe block

`describe 'MyProject' do end`

9) Driver [Dev B]; run `rspec` and confirm that the output is unchanged

10) Driver [Dev B]; initialise a git repository

`git init`

11) Driver [Dev B]; add the my_project_spec file to the repo

`git add spec/my_project_spec.rb`

12) Driver [Dev B]; run `git status` to ensure that git has 'staged' the correct file.

`git init`

You should see output like this:

`# On branch master
#
# Initial commit
#
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#
# new file:   spec/my_project_spec.rb
`
13) Driver [Dev B]; commit the staged change to the git repository

`git commit -m 'first step on our new project'`

14) Driver/Navigator Discussion [Dev A & B]; Inside the describe block you need to add an 'it' statement about one of the very simplest things your project should do.  Discuss this as a pair.  Don't spend hours debating; just make sure that the initial statement about the project makes sense to both of you. You don't have to agree that it is the perfect first statement.  You just want something that is simple.  It can be changed or removed later.  You have bigger plans that this fits into, but they don't have to be completely finalized at this stage. The critical thing is that there is some discussion, but that you also make a decision within a minute or so.

Think of your application (app) code as a ruby robot that will do your bidding.  In order to ask it to do anything you will need to define the language (the programming interface) that you will be using to communicate with it.  This is initial statement should be about the simplest possible thing you can think to say in the language that is the first step on the road to you creating a ruby robot that does your bidding.

15) Driver [Dev B]; type in the it statement that you came up with as a result of your pair discussion

`it 'should be awesome'`

16) Driver [Dev B]; run `rspec` and confirm the output is like the following:

`MyProject
  should be awesome (PENDING: Not yet implemented)

Pending:
  MyProject should be awesome
    # Not yet implemented
    # ./spec/my_project_spec.rb:2

Finished in 0.00023 seconds
1 example, 0 failures, 1 pending`

17) Switch Driver/Navigator Roles

18) Driver [Dev A]; write a line of code that is a method call on your application code.  Don't worry about making an expectation yet.  Just think about the simplest possible thing you could ask your ruby robot.  Feel free to make the method name a longer one, such as 'make_the_title_colour_green' or 'get_my_brand_influencers', e.g. 

`it 'should be awesome' do
  are_you_awesome?
end`

19) Driver [Dev A]; run `rspec` and confirm that you get output like the following:

`MyProject
  should be awesome (FAILED - 1)

Failures:

  1) MyProject should be awesome
     Failure/Error: are_you_awesome?
     NoMethodError:
       undefined method `are_you_awesome?' for #<RSpec::Core::ExampleGroup::Nested_1:0x007fdc4a0f9258>
     # ./spec/my_project_spec.rb:3:in `block (2 levels) in <top (required)>'

Finished in 0.00376 seconds
1 example, 1 failure

Failed examples:

rspec ./spec/my_project_spec.rb:2 # MyProject should be awesome
`

20) Switch Driver/Navigator Roles

21) Driver [Dev B]; Add a require statement to pull in your application code:

`require 'my_project'

describe 'MyProject' do
  it 'should be awesome' do 
    are_you_awesome?
  end
end`

22) Driver [Dev B]; Confirm that you get an error like:

`require': cannot load such file -- my_project (LoadError)`

23) Switch Driver/Navigator Roles

24) Driver [Dev A]; Create a lib directory for your application code

`mkdir lib`

25) Driver [Dev A]; Create a file in the lib directory for your application code:

`touch lib/my_project.rb`

26) Driver [Dev A]; Run `rspec` to confirm we have resolved the 'cannot load such file' error, and we are back to 

`undefined method 'are_you_awesome?'`

27) Switch Driver/Navigator Roles

28) Driver [Dev B]; add the minimum application code possible in order to resolve this error message, e.g. 

`def are_you_awesome?
end`

29) Driver [Dev B]; update the rspec it block to include some sort of expection about the result of calling the method, e.g.

`expect(are_you_awesome?).to be_true`

30) Driver [Dev B]; run `rspec` and confirm you get a test failure like the following:

`
1) MyProject should be awesome
     Failure/Error: expect(are_you_awesome?).to be_true
       expected: true value
            got: nil
     # ./spec/my_project_spec.rb:5:in `block (2 levels) in <top (required)>'
`

31) Switch Driver/Navigator Roles

32) Driver [Dev A]; Make the minimum possible adjustment to the application (app) code so that the test passes, e.g. 

`def are_you_awesome?
  true
end`

33) Driver [Dev A]; Run `rspec` to confirm that the test passes, e.g.  

`MyProject
  should be awesome

Finished in 0.00142 seconds
1 example, 0 failures`

34) Driver [Dev A]; Add a new test that forces more interesting behaviour on the part of the application

... tests about project properties?  did people pair? tdd?









