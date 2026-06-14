## Task Tracking
task management happens through Zenhub

sprints are self-imposed deadlines; while actual hard ones caused by external factors, are expressed via milestones.

![`estimate` section](../../../docs/assets/zenhub_story_points.png) on issues, which they call "Story Points", under our system means apprx number of hours required.
All opened issues should have an estimate attached. Use the **upper** part of the range when not certain.
Very large features can omit it, which would imply that pre-selected sizes are not sufficiently large to cover the expected scope. This is only allowed if the issue has children, and raises questions on why it's not instead a milestone, (through which epics are normally handled).

all tasks past product backlog (sprint backlog and active), must have a person assigned.
However, no such rule exists for tasks oustide, - new issues can be created and kept without anyone yet assigned to them.
Be mindful of intent, - once you assign someone to an issue, they take its ownership. And only one person can be assigned to any one issue (if part of the implementation needs to be delegated, it should be done through creation of a child issue for that part of the work). <!--Done to drive strict ownership of all features. Absence of distinct leader on any task will lead to delegation of responsibility by all participants-->
> you are expected to be aware of all your github notifications, and keep sorting of your Zenhub tasks up-to-date

## Labels
Zenhub's `Priority` labels are to be used always, while `Task Type` is never to be marked.

instead of `Task Type` labels, we define [strict categorical buckets](https://github.com/EV-invest/.github/issues/4#issuecomment-4683864012) for labels used, and express this and more through them.

following buckets exist:

- `type` \
  top-level distinction of __what does working on the issue entails__: {`t:task`, `t:bug`, `t:enhancement`, `t:question`} // `question` is a unification of what could've been `type:decide` + `type:explore`.
  These are shared across all repos; are mutually exclusive; and are obligatory for selection when opening the issue.

- `category` \
  issue's classification: {`cat:docs`, `cat:test`, `cat:ci`, `cat:perf`, etc}
  Specifying is optional; their base is synchronized across all repos, but each can and should define more, for categories specific to its domain.

- `external` \
  meta tags for external sorting/presentation/integrations, like {`ext:good-first-issue`, `ext:help-wanted`, `ext:wontfix`}
  Specifying them is optional; synced across all repos.

## Time Tracking
[Clockify](https://app.clockify.me/calendar) will be integrated later. Manually using it is not realistic, so blocked by tooling automation. <!--Partial implementation already exists in https://github.com/valeratrades/tedi-->
