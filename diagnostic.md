# Ember Components Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components.

    ```md
    a given user could have many events they're attending, which could then be
    divided into subcategories of type of events (concerts, plays, sports) and
    then there could be event details on the lowest level (date, time, venue,
    performers/team)
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember generate component my-map
    ```

1.  What files are edited to produce a component, and what are their
    responsibilities?

    ```md
    The router needs to be edited so ember knows what URL to watch for. The route
    then needs a model hook to know how to get the data associatedwith that
    given URL. The route template then needs to pass this data along to the
    component which then manipulates the data and determines how to display it.
    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` path. What is
    the syntax for loading this component inside that template?

    ```html
    {{my-contact contact=model}} will be inside the app/contacts/template.hbs.
    This will pass the data long to the component.

    From within the 'my-contact' component template you then access this data <body>
    {{contact}}
    </body>
    ```

    Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    {{#each contact.number as  |num|}}
      {{my-contact/my-phone num=num}}
    {{/each}}

    The above will pass the data to the my-phone component. From within this
    component you access it by using {{num}}
    ```
