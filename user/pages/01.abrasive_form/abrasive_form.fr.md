---
title: Kündig AG - Abrasifs
slug: commande-abrasifs
form:
  name: order-form
  action: /commande-abrasifs
  fields:
    - name: firstname
      label: Prénom
      id: firstname
    - name: lastname
      label: Nom de famille
      id: lastname
    - name: company
      label: Entreprise
      id: company
    - name: street
      label: Rue
      id: street
    - name: postal_code
      label: Code postal
      id: postal_code
    - name: city
      label: Ville
      id: city
    - name: email
      label: Adresse électronique
      id: email
    - name: phone
      label: Téléphone
      id: phone
    - type: fieldset
      name: Produits
      id: products
      fields:
        - type: fieldset
          name: Produit 1
          fields:
            - name: amount1
              label: Produit 1 - Quantité
              id: amount1
            - name: dimension1
              label: Produit 1 - Dimension
              id: dimension1
            - name: grain1
              label: Produit 1 - Grain
              id: grain1
            - name: quality1
              label: Produit 1 - Qualité
              id: quality1
        - type: fieldset
          name: Produit 2
          fields:
            - name: amount2
              label: Produit 2 - Quantité
              id: amount2
            - name: dimension2
              label: Produit 2 - Dimension
              id: dimension2
            - name: grain2
              label: Produit 2 - Grain
              id: grain2
            - name: quality2
              label: Produit 2 - Qualité
              id: quality2
        - type: fieldset
          name: Produit 3
          fields:
            - name: amount3
              label: Produit 3 - Quantité
              id: amount3
            - name: dimension3
              label: Produit 3 - Dimension
              id: dimension3
            - name: grain3
              label: Produit 3 - Grain
              id: grain3
            - name: quality3
              label: Produit 3 - Qualité
              id: quality3
        - type: fieldset
          name: Produit 4
          fields:
            - name: amount4
              label: Produit 4 - Quantité
              id: amount4
            - name: dimension4
              label: Produit 4 - Dimension
              id: dimension4
            - name: grain4
              label: Produit 4 - Grain
              id: grain4
            - name: quality4
              label: Produit 4 - Qualité
              id: quality4
        - type: fieldset
          name: Produit 5
          fields:
            - name: amount5
              label: Produit 5 - Quantité
              id: amount5
            - name: dimension5
              label: Produit 5 - Dimension
              id: dimension5
            - name: grain5
              label: Produit 5 - Grain
              id: grain5
            - name: quality5
              label: Produit 5 - Qualité
              id: quality5
        - type: fieldset
          name: Produit 6
          fields:
            - name: amount6
              label: Produit 6 - Quantité
              id: amount6
            - name: dimension6
              label: Produit 6 - Dimension
              id: dimension6
            - name: grain6
              label: Produit 6 - Grain
              id: grain6
            - name: quality6
              label: Produit 6 - Qualité
              id: quality6
        - type: fieldset
          name: Produit 7
          fields:
            - name: amount7
              label: Produit 7 - Quantité
              id: amount7
            - name: dimension7
              label: Produit 7 - Dimension
              id: dimension7
            - name: grain7
              label: Produit 7 - Grain
              id: grain7
            - name: quality7
              label: Produit 7 - Qualité
              id: quality7
    - name: comments
      label: Remarques
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
