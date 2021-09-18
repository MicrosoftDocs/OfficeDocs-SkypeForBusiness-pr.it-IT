---
title: Ottenere i numeri di telefono del servizio per i piani per chiamate
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Scopri come ottenere nuovi numeri di telefono e trasferire o trasferire i numeri esistenti per audioconferenza, operatori automatici e code di chiamata (numeri di servizio) per Teams.
ms.openlocfilehash: 6a065c5661fc4b0a716d2aab31687e20645473fb
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432498"
---
# <a name="srvice-phone-numbers-for-calling-plans"></a>Numeri di telefono di Srvice per Piani per chiamate

**NOTA PER I REVISORI: QUESTO SEMBRA SPECIFICO PER I PIANI DI CHIAMATA. È CONSIGLIABILE SPOSTARLO NEL NODO PIANI PER CHIAMATE?**

Oltre a ottenere numeri di telefono per gli [utenti,](./getting-phone-numbers-for-your-users.md)è possibile ottenere numeri a numero verde o a numero verde per servizi come audioconferenza (per bridge di conferenza), Operatori automatici e Code di chiamata (detti anche numeri di servizio). I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate contemporaneamente, mentre il numero di telefono di un utente può gestire solo alcune chiamate contemporaneamente.
  
> [!NOTE]
> Prima di poter ottenere i numeri verde, è necessario configurare i Crediti comunicazioni. Per altre informazioni, vedere Configurare i crediti [comunicazioni per l'organizzazione.](./set-up-communications-credits-for-your-organization.md)
  
Esistono tre modi per ottenere i numeri di servizio:
  
- **Usare l'Microsoft Teams di amministrazione.** Per alcuni paesi e aree geografiche, è possibile ottenere i numeri di servizio usando l'Microsoft Teams di amministrazione. Vedere [Ottenere nuovi numeri di servizio.](#get-new-service-numbers)

- **Importa i tuoi numeri esistenti.** È possibile trasferire o trasferire i numeri esistenti dal provider di servizi o dal gestore telefonico corrente. Per ulteriori informazioni su come eseguire questa operazione, vedere [Trasferire numeri di telefono in Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).  
  
- **Utilizzare un modulo di richiesta per nuovi numeri.** A volte (a seconda del paese o dell'area geografica) non è possibile ottenere i nuovi numeri di telefono usando l'interfaccia di amministrazione di Microsoft Teams oppure sono necessari numeri di telefono o codici di area specifici. In tal caso, è necessario scaricare un modulo e inviarlo di nuovo a Microsoft. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> I numeri di servizio sono necessari per ottenere una maggiore capacità di chiamata simultanea per un numero specifico. Quando ci trasferisci il numero, puoi contattare il [service desk PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) per assicurarti che il numero di servizio che stai trasferendo abbia una capacità di chiamata simultanea elevata.
  
## <a name="get-new-service-numbers"></a>Ottenere i numeri di servizio

Per ottenere nuovi numeri di servizio, nell'Teams di amministrazione:

1. Nel riquadro di spostamento sinistro passare a **Numeri**  >  **Telefono** vocali e quindi fare clic su **Aggiungi.**

2. Immettere un nome per l'ordine e aggiungere una descrizione.

3. Nella pagina Ubicazione e quantità eseguire le operazioni seguenti:
    - In **Paese o area geografica** selezionare un paese o un'area geografica.
    - In **Tipo di numero** selezionare il tipo di numero di servizio desiderato.
    - In **Posizione** selezionare una posizione. Se è necessario creare una nuova posizione, fare clic **su Aggiungi una posizione.**
    - In **Codice area** selezionare un codice area. 
    - In **Quantità** immettere il numero di numeri desiderato per l'organizzazione e quindi fare clic su **Avanti** per selezionare i numeri.

4. Selezionare i numeri desiderati. Hai 10 minuti per selezionare i numeri di telefono e eseguire l'ordine. Se si prendono più di 10 minuti, i numeri di telefono verranno restituiti al pool di numeri.

5. Quando si è pronti per eseguire l'ordine, fare clic **su Ordina**.

## <a name="port-or-transfer-existing-service-numbers"></a>Portabilità o trasferimento dei numeri di servizio

Per trasferire i numeri di telefono dal provider di servizi o dall'operatore corrente a Teams, è possibile usare la procedura guidata di porting nell'Microsoft Teams di amministrazione. Seguire la procedura descritta in [Trasferire i numeri di telefono Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

Se il paese o l'area geografica non è elencato nella procedura guidata di porting, è possibile inviare manualmente un ordine di trasferimento o passare [a](phone-number-calling-plans/manually-submit-port-order.md) Gestire i numeri di telefono per l'organizzazione, [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)selezionare il paese o l'area geografica e quindi scaricare una lettera di autorizzazione (LOA). Sarà necessario inviare ordini di trasferimento separati per ogni tipo di numero di servizio(ad esempio, numero verde e numero verde) che si trasferirà con un contratto loA. In LOA è necessario selezionare il tipo corretto di numero di servizio. Assicurati di specificare che stai trasferendo un numero di servizio (e non un numero di utente o abbonato) o che la capacità di chiamata simultanea potrebbe non essere sufficiente per gestire i volumi delle chiamate.  

> [!NOTE]
> Se è necessario ottenere più numeri di telefono, [contattare il service desk PSTN.](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)

## <a name="view-the-phone-numbers-for-your-organization"></a>Visualizzare i numeri di telefono dell'organizzazione

Nel riquadro Teams sinistra dell'interfaccia di amministrazione fare clic su Numeri Telefono voce per visualizzare i numeri dell'organizzazione, inclusi la posizione, il tipo di numero e le informazioni  >   sullo stato.

## <a name="assign-service-phone-numbers"></a>Assegnare numeri di telefono del servizio

Dopo aver visualizzato i numeri di servizio, assegnare ogni numero a un bridge di audioconferenza. Vedere Modificare i numeri a pedaggio o a numero verde [sul bridge di audioconferenza.](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

## <a name="related-topics"></a>Argomenti correlati

[Vantaggi offerti dal Sistema telefonico](./here-s-what-you-get-with-phone-system.md)

[Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)