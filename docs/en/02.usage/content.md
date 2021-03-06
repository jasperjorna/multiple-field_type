## Usage[](#usage)

This section will show you how to use the field type via API and in the view layer.


### Setting Values[](#usage/setting-values)

You can set the multiple field type value with a model instance:

    $entry->example = $entry;

You can set the value with a collection of instances too:

    $entry->example = $collection;

Lastly you can set the multiple field type value with an array of entry IDs:

    $entry->example = [7, 8];


### Basic Output[](#usage/basic-output)

The `multiple` field type always returns an `\Anomaly\Streams\Platform\Entry\EntryCollection` instance of related models.

###### Example

    $entry->example; // Collection of models.

###### Twig

    {% for related in entry.example %}
        {{ related.id }}
    {% endfor %}


### Presenter Output[](#usage/presenter-output)

When accessing the field value from a decorated entry model the collection will contain instances of `\Anomaly\Streams\Platform\Entry\EntryPresenter`.

###### Example

    $decorated->example->first()->id;

###### Twig

    {{ decorated.example.first().id }}
