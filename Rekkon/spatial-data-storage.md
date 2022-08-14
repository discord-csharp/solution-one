# Multidimensional Spatial Data Storage

## Summary

Creating a DBMS that supports storing spatial data in multiple dimensions, including indexing using the R*-tree data structure. A university project that is approaching completion for submission will be the center of the talk, as the approaches applied into it will be showcased, additionally consulting the report document for the assignment.

- **Talk Time**: 30-40 min
- **Stage**: Single

## Outline

- Introduction
  - Briefly mention topics of a traditional DBMS (SQL or NOSQL)
  - Specifically mentiion that not all DBMS are for all purposes, some might be specialized further
  - Introduce the application scope of storing spatial data (Google Maps, generally geolocation services)
  - Overview of the components that will be required for building such a DBMS, outlining how C# is a great candidate for the project
- General DBMS
  - Entry tables and entry storage
  - Memory buffers
  - Binary heap in secondary storage
  - Reusing deleted entries' space using a min heap
- The R*-tree
  - How does it look like?
  - Introduction to the B-tree for the unfamiliar
  - Introduction to the R-tree which generalizes the B-tree
  - Additional constraints
  - Mention the limited resources for the implementation of one R*-tree
  - The custom bulk loading algorithm based on STR
- Conclusion, closing
  - A massive thanks to my university professor for catching my interest with the R*-tree data structure
  - Hint for an upcoming personal research about further expanding the R*-tree by permitting rotating rectangles
