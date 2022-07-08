# **Methods of the List Interface**

Since the main concept behind the different types of the lists is the same, the list interface contains the following methods:

## _add(int index, element):_

This method is used to add an element at a particular index in the list. When a single parameter is passed, it simply adds the element at the end of the list.

## _addAll(int index, Collection collection):_

This method is used to add all the elements in the given collection to the list. When a single parameter is passed, it adds all the elements of the given collection at the end of the list.

## _size():_

This method is used to return the size of the list.

## _clear():_

This method is used to remove all the elements in the list. However, the reference of the list created is still stored.

## _remove(int index):_

This method removes an element from the specified index. It shifts subsequent elements(if any) to left and decreases their indexes by 1.

## _remove(element):_

This method is used to remove the first occurrence of the given element in the list.

## _get(int index):_

This method returns elements at the specified index.

## _set(int index, element):_

This method replaces elements at a given index with the new element. This function returns the element which was just replaced by a new element.

## _indexOf(element):_

This method returns the first occurrence of the given element or -1 if the element is not present in the list.

## _lastIndexOf(element):_

This method returns the last occurrence of the given element or -1 if the element is not present in the list.

## _equals(element):_

This method is used to compare the equality of the given element with the elements of the list.

## _hashCode():_

This method is used to return the hashcode value of the given list.

## _isEmpty():_

This method is used to check if the list is empty or not. It returns true if the list is empty, else false.

## _contains(element):_

This method is used to check if the list contains the given element or not. It returns true if the list contains the element.

## _containsAll(Collection collection):_

This method is used to check if the list contains all the collection of elements.

## _sort(Comparator comp):_

This method is used to sort the elements of the list on the basis of the given comparator.
