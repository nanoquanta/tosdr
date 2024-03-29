
## Adding an admin area to the website

On 28 November 2014, Marco and Michiel came together to discuss how we can move forward on the long-standing (and quite obvious) plan to move the https://tosdr.org/ website from static to dynamic (i.e., with a database backend), so that submitting and updating points becomes more efficient.

A year before, Vincent already built the "submit a point" form which allows users to log in with Mozilla Persona, and which adds JSON files to the `points/` folder. Michiel also built the "curator" script (and a bunch of other small scripts) which allows moderators to update the JSON files.

The current consensus is that we should rethink this approach and just switch to a standard web application with a database backend. Marco will be working on this during December. He will be using Meteor, a very well-received web app framework based on node.js and MongoDB, with which it is possible to put together web apps like this very quickly and easily.

Once Marco presents the working application, Michiel will take care of importing the existing data points into the database.

The application distinguishes three type of website users: viewers, reviewers, and moderators.

* Viewers only view the website without logging in.
* Reviewers are logged-in users. Anybody can sign up and become a reviewer to:
  * submit new points,
  * propose the creation of new services and topics if they feel these are missing
  * comment on existing points, services, and topics if they feel they should maybe be edited.
* Moderators are members of the ToS;DR core team and have more privileges than reviewers. They can:
  * approve a point, service, or topic submission,
  * edit and approve a point, service, or topic submission,
  * reject a point, service, or topic submission,
  * edit an existing point, service or topic (possible in reaction to a reviewer comment on there).

When a moderator takes one of these actions, the reviewer is notified of this (Meteor handles this nicely out of the box).

Each time a moderator changes the published data, the JSON are generated as static files, and the html pages are generated from these and also served as static files to the viewers. This ensures that the site stays performant for non-logged-in users, and its appearance and also the API formed by the JSON files do not change.

## Grouping points

We also talked about the way to group points together: for this we have the topics, but we also have the points that affect multiple services introduced by Hugo, and the "cases" proposed by Michiel. This topic was also discussed at the hackathon in Berlin, and probably requires some more discussion, so we decided Marco will leave this out of scope in the first prototype, after which we can have a meeting to discuss what grouping points should look like.

## Other work people can help with

Since we're basically redesigning a big part of how the website works internally, it doesn't make much sense for other people to work on the old submission form and curator scripts at this point. This includes the [low hanging fruit](https://github.com/tosdr/tosdr-build/labels/LowHangingFruit) on the build repo. However, there is always work to do on the browser extensions!