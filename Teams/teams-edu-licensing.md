---
title: Assegnare licenze di Microsoft Teams per l'istruzione
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Informazioni su come assegnare licenze per Microsoft Teams per l'istruzione.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426803"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>Assegnare licenze di Microsoft Teams per l'istruzione

Questo articolo è rivolto agli amministratori IT dell'istruzione che devono assegnare licenze team a docenti, personale e studenti.

Per preparare gli utenti per Teams, è necessario:

1. [Abilitare Microsoft Teams per l'istituto di istruzione nel interfaccia di amministrazione di Microsoft 365](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
2. Assegnare licenze agli account utente per l'accesso ai servizi di Microsoft 365, incluso Teams.

## <a name="ways-to-assign-teams-licenses"></a>Modi per assegnare le licenze di Teams

È possibile assegnare licenze agli account utente:

- Singolarmente o a un piccolo gruppo di utenti nel interfaccia di amministrazione di Microsoft 365.
- Automaticamente tramite l'appartenenza ai gruppi tramite [l'uso di PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) o [di licenze basate su gruppi di Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

Questo articolo illustra come assegnare licenze nel interfaccia di amministrazione di Microsoft 365.

Nel interfaccia di amministrazione di Microsoft 365 è possibile assegnare licenze agli utenti in uno dei casi:

- Pagina **Licenze** per assegnare licenze di prodotto a utenti specifici.
- Pagina **Utenti attivi** per assegnare le licenze degli utenti a prodotti specifici.

> [!NOTE]
> È necessario essere un amministratore globale, un amministratore di fatturazione, un amministratore delle licenze o un amministratore di gestione degli utenti. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Office 365](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Assegnare licenze agli utenti nella pagina Licenze

Nella pagina **Licenze** viene visualizzato un elenco di tutti i prodotti per cui si hanno sottoscrizioni, il numero totale di licenze per ogni prodotto, il numero di licenze assegnate e il numero di licenze disponibili.

1. [Nell'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339) passare [alla pagina](https://go.microsoft.com/fwlink/p/?linkid=842264) **Licenze di fatturazione** > .

2. Selezionare un prodotto per cui si vogliono assegnare le licenze. Microsoft Teams fa parte del Microsoft 365 A1 gratuito SKU Studenti.

3. Selezionare **Assegna licenze**.

4. Nel riquadro **Assegna licenze agli utenti** iniziare a digitare un nome. Dovrebbe essere visualizzato un elenco di nomi.

5. Scegliere il nome che si sta cercando dai risultati per aggiungerlo all'elenco. È possibile aggiungere fino a 20 utenti per volta.

6. Selezionare **Abilita o disabilita le app e i servizi** per assegnare o rimuovere l'accesso a elementi specifici, ad esempio Microsoft Teams. Verificare che **Microsoft Teams** e **Office per il Web (istruzione)** siano selezionati.

7. Al termine, selezionare **Assegna**, quindi selezionare **Chiudi**.

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>Modificare le app e i servizi a cui un utente ha accesso

1. Selezionare la riga che contiene l'utente.

2. Nel riquadro destro selezionare o deselezionare le app e i servizi per i quali si vuole consentire o rimuovere l'accesso.

3. Al termine, selezionare **Salva**, quindi selezionare **Chiudi**.

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>Assegnare licenze agli utenti nella pagina Utenti attivi

1. [Nell'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339) passare alla pagina **Utenti** > [attivi](https://go.microsoft.com/fwlink/p/?linkid=834822).

2. Selezionare i cerchi accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.

3. Nella parte superiore seleziona **Gestisci licenze di prodotto**.

4. Nel riquadro **Gestisci licenze prodotto** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** > **Avanti**.

5. Nel riquadro **Aggiungi a prodotti esistenti** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza che si vuole assegnare agli utenti selezionati. Verificare che **Microsoft Teams** e **Office per il Web (istruzione)** siano selezionati.

   Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti. È possibile limitare i servizi disponibili per gli utenti. Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si vogliono assegnare agli utenti.

6. Nella parte inferiore del riquadro selezionare **Aggiungi** > **chiusura**.
