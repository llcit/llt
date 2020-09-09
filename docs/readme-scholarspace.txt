readme-scholarspace.txt

Repository Layout
-----------------
NFLRC (Community)
- Language Learning and Technology (Community)
    - Volumes  (Collection)
        - Articles (Item)


Vocabularies
-----------------
type - (note distinction between TYPE and TYPE.DCMI) type is a field designated for indicating that a collection item is part of a section within an issue. These sections should be labeled with one of the following:
    * Preface (items that appear at the beginning of issue typically known as Front Matter)
    * Column (articles that group under a "column" title specified in related llt.topic field)
    * Article (articles that group under ordinary issue submissions )
    * Review (articles that are a review)

llt.topic - indicates the title of a column under which an item should be grouped. This field is typically not specified for "Article" or "PREFACE" types, and usually is relevant only columns.

dc.contributor.editor - indicates the item's  editor. Usually this applies to Columns and Reviews because they have editors that are sometimes different from the journal's executive editors.

Data Structure For Front End Toc Layout
-----------------

ITEM_DESC = ['REC OBJECT', 'AUTHOR LIST', 'ABSTRACT TEXT', 'PAGE START']

TOC = {
    TYPE_NAME_A: {
        "subkey_a": {"editors": [], "records": [ITEM_DESC, ITEM_DESC, ITEM_DESC, ...]},
        "subkey_b": {"editors": [], "records": [ITEM_DESC, ITEM_DESC, ITEM_DESC, ...]},
        ...
    },
    TYPE_NAME_B: {
        "subkey_a": {"editors": [], "records": [ITEM_DESC, ITEM_DESC, ITEM_DESC, ...]},
        "subkey_b": {"editors": [], "records": [ITEM_DESC, ITEM_DESC, ITEM_DESC, ...]},
        ...
    },
            
}

Example:

ITEM_DESC = ['REC OBJECT', 'AUTHOR LIST', 'ABSTRACT TEXT', 'PAGE START']

toc = {
'ARTICLE': {'': {"editors": [], "records": [ ITEM_DESC, ITEM_DESC, ITEM_DESC, ]}},
'COLUMN': {
    'llt_topic_a': {"editors": [], "records":  [ ITEM_DESC, ITEM_DESC, ITEM_DESC,  ]},
    'llt_topic_b': {"editors": [], "records":  [ ITEM_DESC, ITEM_DESC, ITEM_DESC, ]},
},
'REVIEW': {
    'llt_topic_a': {"editors": [], "records":  [ ITEM_DESC, ITEM_DESC, ITEM_DESC, ]},
    'llt_topic_b': {"editors": [], "records":  [ ITEM_DESC, ITEM_DESC, ITEM_DESC, ]},
},
'PREFACE': {'': {"editors": [], "records":  [ ITEM_DESC, ITEM_DESC, ITEM_DESC, ]}}
}




    