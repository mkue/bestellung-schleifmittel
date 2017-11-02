---
title: Kündig AG - Abrasives
slug: order-abrasives
form:
  name: order-form
  action: /order-abrasives
  fields:
    - name: firstname
      label: First Name
      id: firstname
    - name: lastname
      label: Last Name
      id: lastname
    - name: company
      label: Company
      id: company
    - name: street
      label: Street
      id: street
    - name: postal_code
      label: Postal code
      id: postal_code
    - name: city
      label: City
      id: city
    - name: email
      label: E-Mail address
      id: email
    - name: phone
      label: Phone
      id: phone
    - type: fieldset
      name: Products
      id: products
      fields:
        - type: fieldset
          name: Product 1
          fields:
            - name: amount1
              label: Product 1 - Amount
              id: amount1
            - name: dimension1
              label: Product 1 - Dimension
              id: dimension1
            - name: grain1
              label: Product 1 - Grain
              id: grain1
            - name: quality1
              label: Product 1 - Quality
              id: quality1
        - type: fieldset
          name: Product 2
          fields:
            - name: amount2
              label: Product 2 - Amount
              id: amount2
            - name: dimension2
              label: Product 2 - Dimension
              id: dimension2
            - name: grain2
              label: Product 2 - Grain
              id: grain2
            - name: quality2
              label: Product 2 - Quality
              id: quality2
        - type: fieldset
          name: Product 3
          fields:
            - name: amount3
              label: Product 3 - Amount
              id: amount3
            - name: dimension3
              label: Product 3 - Dimension
              id: dimension3
            - name: grain3
              label: Product 3 - Grain
              id: grain3
            - name: quality3
              label: Product 3 - Quality
              id: quality3
        - type: fieldset
          name: Product 4
          fields:
            - name: amount4
              label: Product 4 - Amount
              id: amount4
            - name: dimension4
              label: Product 4 - Dimension
              id: dimension4
            - name: grain4
              label: Product 4 - Grain
              id: grain4
            - name: quality4
              label: Product 4 - Quality
              id: quality4
        - type: fieldset
          name: Product 5
          fields:
            - name: amount5
              label: Product 5 - Amount
              id: amount5
            - name: dimension5
              label: Product 5 - Dimension
              id: dimension5
            - name: grain5
              label: Product 5 - Grain
              id: grain5
            - name: quality5
              label: Product 5 - Quality
              id: quality5
        - type: fieldset
          name: Product 6
          fields:
            - name: amount6
              label: Product 6 - Amount
              id: amount6
            - name: dimension6
              label: Product 6 - Dimension
              id: dimension6
            - name: grain6
              label: Product 6 - Grain
              id: grain6
            - name: quality6
              label: Product 6 - Quality
              id: quality6
        - type: fieldset
          name: Product 7
          fields:
            - name: amount7
              label: Product 7 - Amount
              id: amount7
            - name: dimension7
              label: Product 7 - Dimension
              id: dimension7
            - name: grain7
              label: Product 7 - Grain
              id: grain7
            - name: quality7
              label: Product 7 - Quality
              id: quality7
    - name: comments
      label: Comments
      type: textarea
      id: comments
  process:
    - email:
        from: '{{ config.plugins.email.from }}'
        to:
          - m.kuendig@kuendig.ch
          - bestellung-schleifmittel@kuendig.ch
        subject: Bestellung Schleifmittel
        body: '{% include ''forms/data.html.twig'' %}'
    - save:
        fileprefix: feedback-
        dateformat: Ymd-His-u
        extension: txt
        body: '{% include ''forms/data.txt.twig'' %}'
    - display: thankyou
---
