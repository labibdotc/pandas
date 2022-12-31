This change is supposed to fix a problem raised in issues. :issue:`50456`

The problem was that the json object retrieved from the :func:`to_json` inside
:class:`DataFrame` results in a wrong :func:`read_json(json, orient)` when the 
json[columns] is type multiIndex and orient is split.

Fix happens in  :func:`to_json` to store the right column value so that the
roundtrip is successful.