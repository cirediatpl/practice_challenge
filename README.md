# Has Many Through Forms Rails Labs

## Overview

We've looked at setting up the associations behind posts with comments, categories, and users. Now, let's actually give our users the ability to create new comments, users, and categories! For this lab, your models are already stubbed out, but you may need to update them to make your forms work properly.

VenmoUser -< ____ >- Transactions


## Objectives

1. Construct a bi-directional has many through.
2. Identify the join model in a has many through.
3. Construct a nested params hash with data about the primary object and a has many through association.
4. Use the conventional key names for associated data (association_attributes).
5. Name form inputs correctly to create a nested params hash with has many through association data.
6. Define a conventional association writer for the primary model to properly instantiate associations based on the nested params association data.
7. Define a custom association writer for the primary model to properly instantiate associations with custom logic (like unique by name) on the nested params association data.
8. Use fields_for to generate the association fields.

## Instructions

1. Create a form at `transactions#new` to create a new post. The form should include check boxes for us to select two 'VenmoUsers' as well as a text field to create a new VenmoUser. You may do this with a nested form so that our controller stays thin. Also, typing in a `VenmoUser` name that already exists should not create a new category. Instead, if we type in a VenmoUser that already exists, we should select it from the database and associate the transaction we've created with the existing VenmoUser.

2. Create a `transactions#show` page to display the following:
  1. The `subject`, `amount`, and date created of the `transaction`.
  2. All of the VenmoUsers associated with this transaction

3. Create a `show` page for each VenmoUser that displays the  links to all of the transactions a user has made.

## Bonus

+ Can you create a way for each transaction to keep track of which VenmoUser is the sender or the receiver?
+ What other attributes would a VenmoUser need?


## Hints (These may or may not apply)

+ When creating new comments, we should only create a new user if they filled in that input. `accepts_nested_attributes_for` has a `reject_if` option that you can configure to only create new records if all the fields aren't blank.
+ Also, the select box that we use for the users needs to have a blank option –– check out the `include_blank` option for `collection_select`.

## Resources

+ [Accepts Nested Attributes For](http://api.rubyonrails.org/classes/ActiveRecord/NestedAttributes/ClassMethods.html)
+ [Collection Select](http://apidock.com/rails/ActionView/Helpers/FormOptionsHelper/collection_select)
+ [Lab Review](https://www.youtube.com/watch?v=k7s2LjVF3YY)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/has-many-through-forms-rails-labs' title='Has Many Through Forms Rails Labs'>Has Many Through Forms Rails Labs</a> on Learn.co and start learning to code for free.</p>
