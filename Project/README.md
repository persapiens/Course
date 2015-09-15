# Projects

### Teams

Students shall form teams of size 3. No more, no less without instructor approval.

### Milestones

You will deliver your pipeline in 4 milestones, which will include a build component, a testing and analysis component, a deployment component, and a special component.

### Tracks

Milestones generally prescribe a set of high-level design goals, giving much freedom in how you satisfy the goals.

Generally, students will approach each milestone from one of the following tracks.

#### "From Scratch" track

Students can take code started from workshops, and continue to enhance code to be fully functional. This track is best for students that wish to understand concepts from a fundamental level and develop skills that will be useful in learning how to build developer tools. Students have the most freedom in this track, but at the cost of starting from scratch.

#### Technology track

Students can use existing technology solutions to satisfy milestone goals. The benefit of this track is that students will have more familiarity with learning how to configure and customize existing tools. This however comes at the cost of huge learning curves and occasional limitations associated with existing tools.

### Tech Stacks

You are free to choose which ever technology stack you wish; however, consider some of the constraints you will face. If a technology stack significantly lacks several of these aspects, then you should strongly reconsider your choice.

* Configuration management
* Unit tests
* Test coverage
* Plugins available in build server
* Static analysis tools
* Parsing code
* Collecting metrics
* Creating simple services
* Proxy requests, connect with redis

### Other Questions

> **591 and 791 students**. Can a 791 student join a team with a 591 student?

Yes. But it is not recommendated. This will likely cause a 591 student to have to do more work in order to keep up with the demands of the 791 special milestone with only getting normal credit for the work.

> **Switching tracks**. Can we switch tracks between milestones?

Yes. The milestones are generally not dependant on each other. That means, you could decide to use Jenkins in the build Milestone, but then do the static and analysis milestone from scratch without relying on Jenkins. The main exception is that during the last milestone, you'll deliver a presentation of the entire pipeline.

> **Deployed apps**. What do we deploy?

The deployment pipeline is mostly independant of the application deployed. Except, that there will be some dependancies on the technology stack. For example, if you're using Java, then you'll need to find testing and coverage tools that work with Java applications.

> **Existing projects**. Should we deploy existing projects?

Either very simple applications or existing applications are possible. Existing projects will already have the benefit of having build management and testing available. But they will add extra complexity. Simple applications you write will have no build management or tests available, which you will have to provide.
