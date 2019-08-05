---
title: Definizione di regole di normalizzazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Le regole di normalizzazione di Skype for Business Server usano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione accettano il numero di telefono composto da un utente e convertono tale numero nel formato usato internamente da Skype for Business Server. A ogni dial plan devono essere assegnate una o più regole di normalizzazione.
ms.openlocfilehash: e5156816de13a8d59e3e6eea4890046d5b4f586a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187040"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definizione di regole di normalizzazione in Skype for Business Server

Le regole di normalizzazione di Skype for Business Server usano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione accettano il numero di telefono composto da un utente e convertono tale numero nel formato usato internamente da Skype for Business Server. A ogni dial plan devono essere assegnate una o più regole di normalizzazione.

Per informazioni dettagliate sulle regole di normalizzazione, vedere [dial plan e regole](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx)di normalizzazione.

Per informazioni dettagliate su come scrivere espressioni regolari, vedere [espressioni regolari di .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Per definire o modificare una regola di normalizzazione, è possibile usare uno dei metodi seguenti:
- [Usare lo strumento **Costruisci una regola** di normalizzazione](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere e quindi consentire al pannello di controllo di Skype for Business Server di generare il modello di corrispondenza e la regola di traduzione corrispondenti Per te.
- [Scrivere manualmente le espressioni regolari](#create-or-modify-a-normalization-rule-manually) per definire il modello e la regola di traduzione corrispondenti. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Creare o modificare una regola di normalizzazione tramite genera una regola di normalizzazione

Se si vuole creare o modificare una regola di normalizzazione nel pannello di controllo di Skype for Business Server, eseguire la procedura seguente. 

**Per definire una regola utilizzando una regola di normalizzazione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le [autorizzazioni di configurazione](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for business, vedere [installare e aprire strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Opzionale Seguire i passaggi descritti in [creare un dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) tramite il passaggio 11 o [modificare un dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) tramite il passaggio 10. 
4. Nella **nuova regola** di normalizzazione o **Modifica regola**di normalizzazione digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio **5DigitExtension**.
5. Opzionale In **Descrizione**Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".
6. In **genera una regola**di normalizzazione immettere i valori nei campi seguenti:
    - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri composti per cui si vuole che il motivo corrisponda. Ad esempio, digitare **425** se si vuole che il motivo corrisponda ai numeri composti che iniziano con 425.
    - **Length**: specificare il numero di cifre nel modello corrispondente e selezionare se si vuole che il motivo corrisponda esattamente a questa lunghezza, corrispondere a numeri composti con almeno questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.
    - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali che devono essere rimosse dai numeri composti a cui si vuole che corrisponda il motivo.
    - **Cifre da aggiungere**: (facoltativo) specificare le cifre da sommare ai numeri composti per cui si vuole che il motivo corrisponda.
    
    I valori immessi in questi campi si riflettono in **pattern per la corrispondenza** e la **regola di traduzione**. Ad esempio, se si lasciano vuote le **cifre iniziali** , digitare **7** nel campo **lunghezza** selezionare **esattamente**e specificare **0** in **cifre da rimuovere**, l'espressione regolare risultante nel pattern in **modo che corrisponda** è:

    **^ (\d{7}) $**

7. Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti come indicato di seguito:
    - Valore che rappresenta il numero di cifre specificato nel criterio di corrispondenza. Ad esempio, se il modello corrispondente è **^ (\d{7}) $**, allora $1 nella regola di traduzione rappresenta numeri composti da 7 cifre.
    - Opzionale Digitare un valore nel campo **cifre da aggiungere** per specificare le cifre da anteporre al numero tradotto, ad esempio **+ 1425**.
    
    Ad esempio, se **pattern per la corrispondenza** contiene **^ ({7}\d) $** come modello per i numeri composti e la **regola di traduzione** contiene **+ 1425 $1** come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.

8. Opzionale Se la regola di normalizzazione genera un numero di telefono interno all'organizzazione, selezionare **estensione interna**.
9. Opzionale Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.
    > [!Note] 
    > È possibile salvare una regola di normalizzazione che non supera ancora il test e quindi riconfigurarla in un secondo momento. Per informazioni dettagliate, vedere [testare il routing vocale](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Fare clic su **OK** per salvare la regola di normalizzazione.
11. Fare clic su **OK** per salvare il dial plan.
12. Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**. 
    > [!Note]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando Commit tutti per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso nella configurazione del routing vocale](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Creare o modificare manualmente una regola di normalizzazione

Se si vuole creare o modificare manualmente una regola di normalizzazione, eseguire i passaggi seguenti.

**Per definire manualmente una regola di normalizzazione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le [autorizzazioni di configurazione](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Skype for business, vedere [installare e aprire strumenti di amministrazione](../../management-tools/install-and-open-administrative-tools.md).
3. Opzionale Seguire i passaggi descritti in [creare un dial plan](GET LINK AFTER MIGRATION) tramite il passaggio 11 o [modificare un dial plan](GET LINK AFTER MIGRATION) tramite il passaggio 10.  
4. Nella **nuova regola** di normalizzazione o **Modifica regola**di normalizzazione digitare un nome che descriva il criterio di numerazione normalizzato in **nome** , ad esempio denominare la regola di normalizzazione **5DigitExtension**.
5. Opzionale In **Descrizione**Digitare una descrizione della regola di normalizzazione, ad esempio "converte le estensioni a 5 cifre".
6. In **genera una regola**di normalizzazione fare clic su **modifica**.
7. Immettere le opzioni seguenti nell'espressione regolare di tipo:
    - In **corrispondenza di questo modello**specificare il motivo che si vuole usare per corrispondere al numero di telefono chiamato.
    - Nella **regola di traduzione**specificare un motivo per il formato dei numeri di telefono E. 164 tradotti.

    Ad esempio, se si digita **^ (\d{7}) $** in **corrispondenza di questo modello** e **+ 1425 $1** nella **regola di traduzione**, la regola Normalizza 5550100 in + 14255550100.

8. Opzionale Se la regola di normalizzazione genera un numero di telefono interno all'organizzazione, selezionare **estensione interna**.
9. Opzionale Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **immettere un numero da testare**.

    > [!Note]
    > È possibile salvare una regola di normalizzazione che non supera ancora il test e quindi riconfigurarla in un secondo momento. Per informazioni dettagliate, vedere [testare il routing vocale](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Fare clic su **OK** per salvare la regola di normalizzazione.
11. Fare clic su **OK** per salvare il dial plan.
12. Nella pagina **dial plan** fare clic su **commi**t e quindi su **Commit all**. 
