# Introduction #

Jalico is here to speed up development, not to bring fantastic new features. It does once and (presumably) well what programmers tend to program many times in various ways, with variable quality and completeness : listenable containers.


The three founding beliefs behind its design are :
  * event-based programming is good and simple
  * generics are good (but C++'s templates are so much more powerful !)
  * functional programming rocks, and is vastly underexploited in the Java world

# Code pattern addressed by Jalico #

The code pattern that is meant to be addressed here is the following : you have a class Holder that aggregates elements of class Element, and Holder has methods like Holder.addElement(Element), Holder.removeElement(Element), Holder.addElementListener(...), Holder.removeElementListener(...), with the ElementListener class having methods such as elementAdded(ElementEvent), elementRemoved(...), and so on...

Instead of all of this, you simply give Holder a field "ListenableSet

&lt;Element&gt;

 elements" and a getter for this field. In its constructor, Holder registers a listener to the set, so as to react to its modification.