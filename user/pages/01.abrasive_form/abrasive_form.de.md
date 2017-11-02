---
title: Kündig AG - Schleifmittel
slug: bestellung-schleifmittel
form:
  name: order-form
  action: /bestellung-schleifmittel
  fields:
    - name: firstname
      label: Vorname
      id: firstname
    - name: lastname
      label: Nachname
      id: lastname
    - name: company
      label: Firma
      id: company
    - name: street
      label: Strasse
      id: street
    - name: postal_code
      label: PLZ
      id: postal_code
    - name: city
      label: Ort
      id: city
    - name: email
      label: E-Mail
      id: email
    - name: phone
      label: Telefon
      id: phone
    - type: fieldset
      name: Produkte
      id: products
      fields:
        - type: fieldset
          name: Produkt 1
          fields:
            - name: amount1
              label: Produkt 1 - Menge
              id: amount1
            - name: dimension1
              label: Produkt 1 - Dimension
              id: dimension1
            - name: grain1
              label: Produkt 1 - Körnung
              id: grain1
            - name: quality1
              label: Produkt 1 - Qualität
              id: quality1
        - type: fieldset
          name: Produkt 2
          fields:
            - name: amount2
              label: Produkt 2 - Menge
              id: amount2
            - name: dimension2
              label: Produkt 2 - Dimension
              id: dimension2
            - name: grain2
              label: Produkt 2 - Körnung
              id: grain2
            - name: quality2
              label: Produkt 2 - Qualität
              id: quality2
        - type: fieldset
          name: Produkt 3
          fields:
            - name: amount3
              label: Produkt 3 - Menge
              id: amount3
            - name: dimension3
              label: Produkt 3 - Dimension
              id: dimension3
            - name: grain3
              label: Produkt 3 - Körnung
              id: grain3
            - name: quality3
              label: Produkt 3 - Qualität
              id: quality3
        - type: fieldset
          name: Produkt 4
          fields:
            - name: amount4
              label: Produkt 4 - Menge
              id: amount4
            - name: dimension4
              label: Produkt 4 - Dimension
              id: dimension4
            - name: grain4
              label: Produkt 4 - Körnung
              id: grain4
            - name: quality4
              label: Produkt 4 - Qualität
              id: quality4
        - type: fieldset
          name: Produkt 5
          fields:
            - name: amount5
              label: Produkt 5 - Menge
              id: amount5
            - name: dimension5
              label: Produkt 5 - Dimension
              id: dimension5
            - name: grain5
              label: Produkt 5 - Körnung
              id: grain5
            - name: quality5
              label: Produkt 5 - Qualität
              id: quality5
        - type: fieldset
          name: Produkt 6
          fields:
            - name: amount6
              label: Produkt 6 - Menge
              id: amount6
            - name: dimension6
              label: Produkt 6 - Dimension
              id: dimension6
            - name: grain6
              label: Produkt 6 - Körnung
              id: grain6
            - name: quality6
              label: Produkt 6 - Qualität
              id: quality6
        - type: fieldset
          name: Produkt 7
          fields:
            - name: amount7
              label: Produkt 7 - Menge
              id: amount7
            - name: dimension7
              label: Produkt 7 - Dimension
              id: dimension7
            - name: grain7
              label: Produkt 7 - Körnung
              id: grain7
            - name: quality7
              label: Produkt 7 - Qualität
              id: quality7
    - name: comments
      label: Bemerkungen
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
