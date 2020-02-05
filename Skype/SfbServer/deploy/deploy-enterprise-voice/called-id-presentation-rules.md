---
title: Creare o modificare una regola di traduzione per la presentazione di ID chiamata in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Riepilogo: informazioni su come definire una regola di traduzione usando lo strumento crea una regola di traduzione in Skype for Business Server.'
ms.openlocfilehash: 1a1f363ad157775395f77ef3e3c2915e9226bfd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768199"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Creare o modificare una regola di traduzione per la presentazione di ID chiamata in Skype for Business Server

**Riepilogo:** Informazioni su come definire una regola di traduzione usando lo strumento crea una regola di traduzione in Skype for Business Server.

Seguire questa procedura se si vuole definire una regola di traduzione immettendo un set di valori nello strumento **Crea una regola di traduzione** e abilitando il pannello di controllo di Skype for Business Server per generare il modello di corrispondenza corrispondente e la regola di traduzione. In alternativa, è possibile eseguire manualmente un'espressione regolare di scrittura per definire il modello e la regola di traduzione corrispondenti. Per informazioni dettagliate, vedere [creare o modificare manualmente una regola di traduzione](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Per definire una regola usando lo strumento crea una regola di traduzione

1. Aprire il pannello di controllo di Skype for Business Server.

2. Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Skype for Business Server](configure-trunk-without-media-bypass.md) tramite il passaggio 9.

3. In **nome** nella pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.

4. Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le chiamate interurbane internazionali degli Stati Uniti.

5. Nella sezione **genera una regola di traduzione** della finestra di dialogo immettere i valori nei campi seguenti:

   - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si vuole che corrisponda il motivo. Ad esempio, immettere + in questo campo per abbinare i numeri nel formato E. 164 (che iniziano con +).

   - **Length**: specificare il numero di cifre nel criterio di corrispondenza e selezionare se si vuole che il pattern corrisponda a numeri di lunghezza uguale a quella specificata, almeno questa lunghezza o qualsiasi lunghezza. Ad esempio, immettere 11 e selectAt almeno nell'elenco a discesa in base a numeri che hanno una lunghezza di almeno 11 cifre.

   - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da eliminare. Ad esempio, immettere 1 per eliminare il + dall'inizio del numero.

   - **Cifre da aggiungere**: (facoltativo) specificare le cifre da anteporre ai numeri tradotti. Ad esempio, immetti 011 se vuoi che 011 venga anteposto ai numeri tradotti quando viene applicata la regola.

     I valori immessi in questi campi si riflettono nei campi della regola **per la corrispondenza** e la **traduzione** . Ad esempio, se specifichi i valori di esempio precedenti, l'espressione regolare risultante nel campo **pattern to match** è:

     ^\+(\d{9}\d +) $

     Il campo della **regola di traduzione** specifica un modello per il formato dei numeri tradotti. Questo modello include due parti:

   - Un valore, ad esempio $1, che rappresenta il numero di cifre nel modello corrispondente

   - Opzionale Un valore che puoi anteporre immettendolo nel campo **cifre da aggiungere**

     Usando i valori di esempio precedenti, viene visualizzato 011 $1 nel campo della **regola di traduzione** .

     Quando viene applicata questa regola di traduzione, + 441235551010 diventa 011441235551010.

6. Fare clic su **OK** per salvare la regola di traduzione.

7. Fare clic su **OK** per salvare la configurazione trunk.

8. Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.

   > [!NOTE]
   > Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

### <a name="to-define-a-translation-rule-manually"></a>Per definire manualmente una regola di traduzione

1. Aprire il pannello di controllo di Skype for Business Server

2. Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Skype for Business Server](configure-trunk-without-media-bypass.md) tramite il passaggio 9.

3. Nel campo **nome** della pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.

4. Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le chiamate interurbane internazionali degli Stati Uniti.

5. Fare clic su **modifica** nella parte inferiore della sezione **Compila una regola di traduzione** .

6. Immettere le opzioni seguenti nell' **espressione regolare di tipo**:

   - In **Confronta questo modello**, specifica il motivo che verrà usato per corrispondere ai numeri da tradurre.

   - Nella **regola di traduzione**specificare un motivo per il formato dei numeri tradotti.

     Ad esempio, se si digita ^\+(\d{9}\d +) $ in **corrisponde a questo modello** And011 $1 nella **regola di traduzione**, la regola tradurrà + 441235551010 in 011441235551010.

7. Fare clic su **OK** per salvare la regola di traduzione.

8. Fare clic su **OK** per salvare la configurazione trunk.

9. Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

## <a name="see-also"></a>Vedere anche

[Configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Configurare un trunk senza bypass multimediale in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business](voice-route-config-changes.md)

[Distribuire il bypass multimediale in Skype for Business Server](deploy-media-bypass.md)

