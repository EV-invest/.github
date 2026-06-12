## Task Tracking
task management happens through Zenhub

sprints are self-imposed deadlines; while actual hard ones caused by external factors, are expressed via milestones.

![`estimate` section](../../../assets/zenhub_story_points.png) on issues, which they call "Story Points", under our system means apprx number of hours required.
Very large features can omit it, which would imply that pre-selected sizes are not sufficiently large to cover the expected scope. This is only allowed if the issue has children, and raises questions on why it's not instead a milestone, (through which epics are normally handled).

people are assigned to the task only when this piece of work becomes active, and their action is expected. Don't assign roles while the item is in the backlog.
> you are expected to be aware of all your github notifications, and keep your active ZenHub tasks' sorting up-to-date

## Labels
Zenhub's `Priority` labels are to be used always, while `Task Type` is never to be marked.

instead of `Task Type` labels, we define [strict categorical buckets](https://github.com/EV-invest/.github/issues/4#issuecomment-4683864012) for labels used, and express this and more through them.

following buckets exist:

- `type` \
  top-level distinction of __what does working on the issue entails__: {`type:task`, `type:bug`, `type:enhancement`, `type:decision`}
  These are shared across all repos; are mutually exclusive; and are obligatory for selection when opening the issue.

- `category` \
  issue's classification: {`cat:docs`, `cat:test`, `cat:ci`, `cat:perf`, etc}
  Their base is synchronized across all repos, but each can and should define more, for categories specific to its domain.

- `external` \
  meta tags for external sorting/presentation/integrations, like {`external:good-first-issue`, `external:help-wanted`, `external:wontfix`}
  Adding them is optional; synced across all repos.

## Time Tracking
[Clockify](https://app.clockify.me/calendar) will be integrated later. Manually using it is not realistic, so blocked by tooling automation. <!--Partial implementation already exists in https://github.com/valeratrades/tedi-->
