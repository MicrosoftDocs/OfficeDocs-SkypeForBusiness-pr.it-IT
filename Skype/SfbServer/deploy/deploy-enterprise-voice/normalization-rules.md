---
title: Creare o modificare una regola di normalizzazione in Skype for Business
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Riepilogo: informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.'
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830766"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Creare o modificare una regola di normalizzazione in Skype for Business

**Riepilogo:** Informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.

Definire, creare e modificare le regole di normalizzazione in Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Per definire una regola di normalizzazione tramite La creazione di una regola di normalizzazione

1. Aprire il Pannello di controllo di Skype for Business Server

2. (Facoltativo) Seguire i passaggi descritti in Creare o modificare un [dial plan in Skype for Business Server](dial-plans.md) fino al passaggio 11 o modificare un dial plan fino [al](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) passaggio 10.

3. In **Nuova regola di normalizzazione** o Modifica regola di **normalizzazione** digitare un nome che descriva il modello di numero normalizzato in **Nome** (ad esempio, 5DigitExtension).

4. (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".

5. In **Crea regola di normalizzazione** immettere valori nei campi seguenti:

   - **Cifre iniziali** (facoltativo) Specificare le cifre iniziali dei numeri composto a cui si desidera che il formato corrisponda. Ad esempio, digitare 425 se si desidera che il formato corrisponda ai numeri composto che iniziano con 425.

   - **Lunghezza** Specificare il numero di cifre nel formato corrispondente e specificare se si desidera che il formato corrisponda esattamente a questa lunghezza, che corrisponda a numeri composto almeno di questa lunghezza o che corrispondano a numeri di qualsiasi lunghezza.

   - **Cifre da rimuovere** (facoltativo) Specificare il numero di cifre iniziale da rimuovere dai numeri composto a cui si desidera che il formato corrisponda.

   - **Cifre da aggiungere** (facoltativo) Specificare le cifre da aggiungere ai numeri composto a cui si desidera che il formato corrisponda.

     I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se, ad esempio, si lasciano vuote  le cifre di inizio, digitare 7 nel campo Lunghezza e selezionare Esattamente e specificare 0 in **Cifre** da rimuovere, l'espressione regolare risultante nel formato da trovare **corrisponderà** alla seguente: 

     ^(\d {7} )$

6. In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:

   - Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza. Ad esempio, se il criterio di corrispondenza è ^(\d )$, $1 nella regola di conversione {7} rappresenta numeri composto a 7 cifre.

   - (Facoltativo) Digitare un valore nel **campo Cifre da** aggiungere per specificare le cifre da anteporre al numero convertito, ad esempio+1425.

     Ad esempio, se **Pattern per** la corrispondenza contiene^(\d )$ come modello per i numeri composto e la regola di conversione contiene +1425$1 come modello per i numeri di telefono {7} E.164, la regola normalizza da 5550100 a +14255550100. 

7. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

8. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

    > [!NOTE]
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per informazioni dettagliate, vedere [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

### <a name="to-define-a-normalization-rule-manually"></a>Per definire manualmente una regola di normalizzazione

1. Aprire il Pannello di controllo di Skype for Business Server

2. (Facoltativo) Seguire i passaggi descritti in [Creare o modificare un dial plan in Skype for Business Server.](dial-plans.md)

3. In Nuova regola  **di normalizzazione** o Modifica regola di normalizzazione digitare un nome che descriva il modello di numero normalizzato in **Nome** (ad esempio, assegnare alla regola di normalizzazione il nome5DigitExtension).

4. (Facoltativo) Nel **campo Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte gli interni a 5 cifre".

5. In **Crea regola di normalizzazione fare** clic su **Modifica.**

6. Immettere quanto segue in **Digita espressione regolare**:

   - In **Corrispondenza a questo modello** specificare il formato che si desidera utilizzare per la corrispondenza con il numero di telefono composto.

   - In **Regola di conversione** specificare un formato per il formato dei numeri di telefono E.164 convertiti.

     Ad esempio, se si immette ^(\d )$ in Corrispondenza a questo modello e {7} +1425$1 nella regola di conversione, la regola normalizza da 5550100 a +14255550100.  

7. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

8. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai.** I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.


