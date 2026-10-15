System Database Diagram
========================

This diagram shows the database architecture of ABAS..

.. mermaid::

   erDiagram
      CUSTOMER ||--o{ ORDER : places
      ORDER ||--|{ ORDER_ITEM : contains
      PRODUCT ||--o{ ORDER_ITEM : includes
      CUSTOMER {
          string id
          string name
          string email
      }
      ORDER {
          string id
          date orderDate
          string status
      }
      PRODUCT {
          string id
          string name
          float price
      }
      ORDER_ITEM {
          int quantity
          float price
      }

Go back
-------

Return to the :ref:`architecture-overview` section.
