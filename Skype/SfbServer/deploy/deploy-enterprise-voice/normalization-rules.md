---
title: Creare o modificare una regola di normalizzazione in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Riepilogo: informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.'
---

# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Creare o modificare una regola di normalizzazione in Skype for Business

**Riepilogo:** Informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.

Definire, creare e modificare le regole di normalizzazione in Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Per definire una regola di normalizzazione tramite La creazione di una regola di normalizzazione

1. Aprire Skype for Business Server pannello di controllo

2. (Facoltativo) Seguire i passaggi descritti in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 o [Modify a Dial Plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) through step 10.

3. In **Nuova regola di normalizzazione** o Modifica regola di **normalizzazione** digitare un nome che descriva il modello di numero normalizzato in **Nome** (ad esempio, 5DigitExtension).

4. (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".

5. In **Crea regola di normalizzazione** immettere valori nei campi seguenti:

   - **Cifre iniziali** (facoltativo) Specificare le cifre iniziali dei numeri composto a cui si desidera che il formato corrisponda. Ad esempio, digitare 425 se si desidera che il formato corrisponda ai numeri composto che iniziano con 425.

   - **Lunghezza** Specificare il numero di cifre nel modello di corrispondenza e specificare se si desidera che il motivo corrisponda esattamente a questa lunghezza, che corrisponda a numeri composto di almeno questa lunghezza o che corrispondano a numeri di qualsiasi lunghezza.

   - **Cifre da rimuovere** (facoltativo) Specificare il numero di cifre iniziale da rimuovere dai numeri composto a cui si desidera che il formato corrisponda.

   - **Cifre da aggiungere** (facoltativo) Specificare le cifre da aggiungere ai numeri composto a cui si desidera che il formato corrisponda.

     I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se ad esempio si lascia vuota l'opzione Cifre iniziale, digitare 7  nel campo Lunghezza e selezionare Esattamente e specificare 0 in **Cifre** da rimuovere, l'espressione regolare risultante nel campo **Motivo** da trovare corrisponderà alla seguente:

     ^(\d{7})$

6. In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:

   - Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza. Ad esempio, se il criterio di corrispondenza è ^(\d{7})$, $1 nella regola di conversione rappresenta numeri composto a 7 cifre.

   - (Facoltativo) Digitare un valore nel campo **Cifre** da aggiungere per specificare le cifre da anteporre al numero convertito, ad esempio+1425.

     Ad esempio, se Pattern **to match** contiene^(\d{7})$ come modello per i numeri composto e **la** regola di conversione contiene +1425$1 come modello per i numeri di telefono E.164, la regola normalizza da 5550100 a +14255550100.

7. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

8. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

    > [!NOTE]
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per informazioni dettagliate, vedere [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

### <a name="to-define-a-normalization-rule-manually"></a>Per definire manualmente una regola di normalizzazione

1. Aprire Skype for Business Server pannello di controllo

2. (Facoltativo) Seguire i passaggi descritti in [Creare o modificare un dial plan in Skype for Business Server](dial-plans.md).

3. In **Nuova regola di normalizzazione** o Modifica regola di normalizzazione digitare un nome che descriva il modello di numero normalizzato in **Nome**( ad esempio, denomare la regola di normalizzazione5DigitExtension).

4. (Facoltativo) Nel **campo** Descrizione digitare una descrizione della regola di normalizzazione, ad esempio "Converte estensioni di 5 cifre".

5. In **Crea regola di normalizzazione fare** clic su **Modifica**.

6. Immettere quanto segue in **Digita espressione regolare**:

   - In **Corrispondenza questo modello** specificare il modello che si desidera utilizzare per corrispondere al numero di telefono composto.

   - In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti.

     Ad esempio, se si immette ^(\d{7}) **$ in Corrispondenza** questo modello e +1425$ **1 in Regola** di conversione, la regola normalizza da 5550100 a +14255550100.

7. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

8. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.