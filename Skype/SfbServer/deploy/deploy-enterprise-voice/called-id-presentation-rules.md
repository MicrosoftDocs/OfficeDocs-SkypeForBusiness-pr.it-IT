---
title: Creare o modificare una regola di conversione per la presentazione ID denominata in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Riepilogo: informazioni su come definire una regola di conversione utilizzando lo strumento Crea regola di conversione in Skype for Business Server.'
ms.openlocfilehash: 0f8f511996c8d3a578087c9f4252492fa03ef4237688bcaf68a04f09ed944116
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281289"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Creare o modificare una regola di conversione per la presentazione ID denominata in Skype for Business Server

**Riepilogo:** Scopri come definire una regola di conversione usando lo strumento Crea una regola di conversione in Skype for Business Server.

Seguire questa procedura se si desidera definire una regola di  conversione immettendo un set di valori nello strumento Crea una regola di conversione e abilitando il Pannello di controllo di Skype for Business Server per generare automaticamente il modello di corrispondenza e la regola di conversione corrispondenti. In alternativa, è possibile scrivere manualmente un'espressione regolare per definire il formato e la regola di conversione corrispondenti. Per informazioni dettagliate, vedere [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Per definire una regola tramite lo strumento Crea regola di conversione

1. Aprire Skype for Business Server Pannello di controllo.

2. Per iniziare a definire una regola di conversione, seguire i passaggi descritti in Configure a trunk with media bypass in Skype for Business Server through step 10 o Configure a trunk without media bypass in Skype for Business Server through step 9.To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or Configure a trunk without media bypass in [Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.

3. In **Nome** nella pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome descrittivo del formato del numero da convertire.

4. (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio Composizione interurbana internazionale negli Stati Uniti.

5. Nella sezione **Crea regola di conversione** della finestra di dialogo immettere i valore nei campi seguenti:

   - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si desidera corrisponda il formato. Ad esempio, immettere + in questo campo per specificare una corrispondenza con i numeri nel formato E.164, che iniziano con +.

   - **Lunghezza**: specificare il numero di cifre nel formato e specificare se si desidera applicare il formato ai numeri esattamente di questa lunghezza, almeno di questa lunghezza o di qualsiasi lunghezza. Ad esempio, immettere 11 e selezionare Almeno nell'elenco a discesa per trovare una corrispondenza con numeri di almeno 11 cifre.

   - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da rimuovere. Ad esempio, immettere 1 per rimuovere il segno + dall'inizio del numero.

   - **Prefisso**: (facoltativo) specificare le cifre da aggiungere all'inizio dei numeri convertiti. Ad esempio, immettere 011 se si desidera aggiungere 011 all'inizio dei numeri convertiti quando si applica questa regola.

     I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se si specificano i valori di esempio precedenti, ad esempio, l'espressione regolare risultante nel campo **Formato per corrispondenza** sarà:

     ^\+(\d {9} \d+)$

     Nel campo **Regola di conversione** specificare un modello per il formato dei numeri convertiti. Il modello è composto da due parti:

   - Un valore (ad esempio $1) che rappresenta il numero di cifre nel formato corrispondente

   - (Facoltativo) Un valore che è possibile aggiungere all'inizio del numero immettendolo nel campo **Prefisso**

     In base ai valori di esempio precedenti, nel campo Regola di conversione viene visualizzato **011$1**.

     Con l'applicazione di questa regola di conversione il numero +441235551010 diventa 011441235551010.

6. Fare clic su **OK** per salvare la regola di conversione.

7. Fare clic su **OK** per salvare la configurazione del trunk.

8. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.

   > [!NOTE]
   > Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

### <a name="to-define-a-translation-rule-manually"></a>Per definire manualmente una regola di conversione

1. Aprire Skype for Business Server pannello di controllo

2. Per iniziare a definire una regola di conversione, seguire i passaggi descritti in Configure a trunk with media bypass in Skype for Business Server through step 10 o Configure a trunk without media bypass in Skype for Business Server through step 9.To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or Configure a trunk without media bypass in [Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.

3. Nel campo **Nome** della pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome che descriva il formato del numero da convertire.

4. (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio Composizione interurbana internazionale negli Stati Uniti.

5. Fare clic su **Modifica** nella parte inferiore della sezione **Crea regola di conversione**.

6. Immettere quanto segue in **Digita espressione regolare**:

   - In **Trova corrispondenza per questo formato** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.

   - In **Regola di conversione** specificare un modello per il formato dei numeri convertiti.

     Ad esempio, se si immette ^ (\d \d+)$ in Corrispondenza questo modello e \+ {9} 011$1 in  Regola di conversione, la regola convertirà +441235551010 in 011441235551010.

7. Fare clic su **OK** per salvare la regola di conversione.

8. Fare clic su **OK** per salvare la configurazione del trunk.

9. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

## <a name="see-also"></a>Vedere anche

[Configurare un trunk con bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Configurare un trunk senza bypass multimediale in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for Business](voice-route-config-changes.md)

[Distribuire il bypass multimediale in Skype for Business Server](deploy-media-bypass.md)