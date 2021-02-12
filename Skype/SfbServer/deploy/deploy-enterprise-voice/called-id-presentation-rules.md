---
title: Creare o modificare una regola di conversione per la presentazione ID chiamata in Skype for Business Server
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
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804196"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Creare o modificare una regola di conversione per la presentazione ID chiamata in Skype for Business Server

**Riepilogo:** Informazioni su come definire una regola di conversione usando lo strumento Crea regola di conversione in Skype for Business Server.

Segui questi passaggi se vuoi definire una regola di conversione immettendo un set di valori nello strumento Crea regola di conversione e abilitando il Pannello di controllo di Skype for Business Server per generare automaticamente il modello e la regola di conversione corrispondenti.  In alternativa, è possibile scrivere manualmente un'espressione regolare per definire il formato e la regola di conversione corrispondenti. Per informazioni dettagliate, vedere [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Per definire una regola tramite lo strumento Crea regola di conversione

1. Aprire il Pannello di controllo di Skype for Business Server.

2. Per iniziare a definire una regola di conversione, seguire i passaggi descritti in Configurare un trunk con bypass multimediale [in Skype for Business Server](configure-trunk-with-media-bypass.md) fino al passaggio 10 o configurare un trunk senza bypass multimediale in Skype for Business [Server](configure-trunk-without-media-bypass.md) fino al passaggio 9.

3. In **Nome** nella pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome descrittivo del formato del numero da convertire.

4. (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio Composizione interurbana internazionale degli Stati Uniti.

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

1. Aprire il Pannello di controllo di Skype for Business Server

2. Per iniziare a definire una regola di conversione, seguire i passaggi descritti in Configurare un trunk con bypass multimediale [in Skype for Business Server](configure-trunk-with-media-bypass.md) fino al passaggio 10 o configurare un trunk senza bypass multimediale in Skype for Business [Server](configure-trunk-without-media-bypass.md) fino al passaggio 9.

3. Nel campo **Nome** della pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome che descriva il formato del numero da convertire.

4. (Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio Composizione interurbana internazionale degli Stati Uniti.

5. Fare clic su **Modifica** nella parte inferiore della sezione **Crea regola di conversione**.

6. Immettere quanto segue in **Digita espressione regolare**:

   - In **Trova corrispondenza per questo formato** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.

   - In **Regola di conversione** specificare un modello per il formato dei numeri convertiti.

     Ad esempio, se si immette ^ (\d \d+)$ in Corrispondenza a questo modello e 011$1 nella regola di conversione, la regola convertirà \+ {9} +441235551010 in 011441235551010.  

7. Fare clic su **OK** per salvare la regola di conversione.

8. Fare clic su **OK** per salvare la configurazione del trunk.

9. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

## <a name="see-also"></a>Vedere anche

[Configurare un trunk con bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Configurare un trunk senza bypass multimediale in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Pubblicare modifiche in sospeso nella configurazione del routing vocale in Skype for Business](voice-route-config-changes.md)

[Distribuire il bypass multimediale in Skype for Business Server](deploy-media-bypass.md)

