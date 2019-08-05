---
title: Creare o modificare una regola di normalizzazione in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Riepilogo: informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.'
ms.openlocfilehash: 4739bdb50e0a76c088cb6129539438c1ac6d795a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195763"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Creare o modificare una regola di normalizzazione in Skype for business

**Riepilogo:** Informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.

Definire, creare e modificare le regole di normalizzazione in Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Per definire una regola di normalizzazione tramite genera una regola di normalizzazione

1. Aprire il pannello di controllo di Skype for Business Server

2. Opzionale Seguire i passaggi descritti in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) tramite il passaggio 11 o [modificare un dial plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) tramite il passaggio 10.

3. Nella **nuova regola** di normalizzazione o **Modifica regola**di normalizzazione digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio 5DigitExtension.

4. Opzionale In **Descrizione**Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".

5. In **genera una regola**di normalizzazione immettere i valori nei campi seguenti:

   - **Cifre iniziali** Opzionale Specificare le cifre iniziali dei numeri composti per cui si vuole che il motivo corrisponda. Ad esempio, type425 se si vuole che il motivo corrisponda ai numeri composti che iniziano con 425.

   - **Lunghezza** Specificare il numero di cifre nel modello corrispondente e selezionare se si vuole che il motivo corrisponda esattamente a questa lunghezza, corrispondere a numeri composti con almeno questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.

   - **Cifre da rimuovere** Opzionale Specificare il numero di cifre iniziali da rimuovere dai numeri composti per cui si vuole che il motivo corrisponda.

   - **Cifre da aggiungere** Opzionale Specificare le cifre da aggiungere ai numeri composti per cui si vuole che il motivo corrisponda.

     I valori immessi in questi campi si riflettono in **pattern per la corrispondenza** e la **regola di traduzione**. Ad esempio, se si lasciano vuote le **cifre iniziali** , Type7 nel campo **lunghezza** e si seleziona **esattamente**e si specificano 0 in **cifre da rimuovere**, l'espressione regolare risultante nel **pattern da corrispondere** è:

     ^ (\d{7}) $

6. Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti come indicato di seguito:

   - Valore che rappresenta il numero di cifre specificato nel criterio di corrispondenza. Ad esempio, se il modello corrispondente è ^ (\d{7}) $ quindi $1 nella regola di traduzione rappresenta numeri composti da 7 cifre.

   - Opzionale Digitare un valore nel campo **cifre da aggiungere** per specificare le cifre da anteporre al numero tradotto, ad esempio + 1425.

     Ad esempio, se **pattern per la corrispondenza** contiene ^ ({7}\d) $ come modello per i numeri composti e la **regola di traduzione** contiene + 1425 $1 come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.

7. Opzionale Se la regola di normalizzazione genera un numero di telefono interno all'organizzazione, selezionare **estensione interna**.

8. Opzionale Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.

    > [!NOTE]
    > È possibile salvare una regola di normalizzazione che non supera ancora il test e quindi riconfigurarla in un secondo momento. Per informazioni dettagliate, vedere [testare il routing vocale](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

### <a name="to-define-a-normalization-rule-manually"></a>Per definire manualmente una regola di normalizzazione

1. Aprire il pannello di controllo di Skype for Business Server

2. Opzionale Seguire i passaggi descritti in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md).

3. Nella **nuova regola** di normalizzazione o **Modifica regola**di normalizzazione digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio denominare la rule5DigitExtension di normalizzazione.

4. Opzionale In campo **Descrizione** Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".

5. In **genera una regola**di normalizzazione fare clic su **modifica**.

6. Immettere le opzioni seguenti nell' **espressione regolare di tipo**:

   - In **corrispondenza di questo modello**specificare il motivo che si vuole usare per corrispondere al numero di telefono chiamato.

   - Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti.

     Ad esempio, se si digita ^ (\d{7}) $ in **corrispondenza di questo modello** e + 1425 $1 nella **regola di traduzione**, la regola Normalizza 5550100 in + 14255550100.

7. Opzionale Se la regola di normalizzazione genera un numero di telefono interno all'organizzazione, selezionare **estensione interna**.

8. Opzionale Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.


