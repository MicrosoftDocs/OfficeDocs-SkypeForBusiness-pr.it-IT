---
title: Accedere a Microsoft Teams con l'autenticazione moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Come accedere a Microsoft Teams usando l'autenticazione moderna. Include come ignorare l'aggiunta automatica del nome utente UPN quando gli utenti accedono con un'impostazione che indica a Windows di ignorare l'UPN.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: f86568f92f2b758ae48062c84b330461743ef178
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116642"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Accedere a Microsoft Teams con l'autenticazione moderna
==========================

Microsoft Teams usa l'autenticazione moderna per mantenere l'esperienza di accesso più semplice e sicura. Per scoprire in che modo gli utenti accedono a Teams, leggere [Accedere a Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Funzionamento dell'autenticazione moderna

L'autenticazione moderna è un processo che informa Teams che gli utenti hanno già immesso le loro credenziali, come l'indirizzo di posta elettronica aziendale e la password, e che non è necessario immetterle di nuovo per avviare l'app. L'esperienza varia in base a un paio di fattori, ad esempio se gli utenti lavorano in Windows o in Mac. Inoltre, varia a seconda che l'organizzazione abbia abilitato l'autenticazione a un fattore o l'autenticazione a più fattori. L'autenticazione a più fattori implica in genere la verifica delle credenziali tramite un telefono, l'inserimento di un codice univoco, l'immissione di un PIN o la presentazione di un'identificazione personale. Ecco una panoramica di ogni scenario di autenticazione moderna.

### <a name="windows-users"></a>Utenti di Windows 

- Se gli utenti hanno già eseguito l'accesso ad altre app di Office tramite il loro account di Office 365 Enterprise, all'avvio di Teams vengono portati direttamente all'app. Non è necessario immettere le credenziali.

- Se gli utenti non hanno eseguito l'accesso al proprio account di Office 365 Enterprise, all'avvio di Teams viene loro chiesto di fornire l'autenticazione a uno o a più fattori (SFA o MFA), in base alla scelta dell'organizzazione.

- Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio, all'avvio di Teams potrebbero dover eseguire un ulteriore passaggio di autenticazione, a seconda che l'organizzazione abbia scelto di richiedere l'autenticazione MFA o che il computer in uso richieda già l'autenticazione MFA per accedere. Se il computer in uso richiede già l'autenticazione MFA per accedere, aprendo Teams l'app viene avviata automaticamente.

- Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio e **non si vuole che il nome utente sia precompilato nella schermata di accesso a Teams**, gli amministratori possono impostare la chiave seguente del Registro di sistema di Windows per disattivare il prepopolamento del nome utente (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > La precompilazione del nome utente per i nomi che terminano in ".local" o ".corp" è disattivata per impostazione predefinita, non è necessario impostare una chiave del Registro di sistema allo scopo. 


### <a name="mac-users"></a>Utenti Mac 

Quando gli utenti avviano Teams, il computer non sarà in grado di recuperare le credenziali dall'account di Office 365 Enterprise o da qualsiasi altra applicazione di Office. Verrà visualizzato un messaggio che chiede l'autenticazione SFA o MFA, in base alle impostazioni dell'organizzazione. Una volta immesse le credenziali, gli utenti non dovranno fornirle di nuovo. Da quel momento in poi, Teams si avvierà automaticamente ogni volta che lavorano con lo stesso computer.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Cambiare account dopo aver completato l'autenticazione moderna

Se gli utenti stanno lavorando su un computer aggiunto a un dominio, ad esempio se il tenant ha abilitato Kerberos, non possono cambiare account utente dopo aver completato l'autenticazione moderna. Se gli utenti non stanno lavorando su un computer aggiunto a un dominio, possono cambiare account.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Disconnessione da Teams dopo aver completato l'autenticazione moderna
Per disconnettersi da Teams, gli utenti possono fare clic sull'immagine del profilo nella parte superiore dell'app e quindi selezionare **Disconnetti**. Possono anche fare clic con il pulsante destro del mouse sull'icona dell'app nella barra delle applicazioni e scegliere **Disconnetti**. Dopo la disconnessione da Teams, per avviare l'app è necessario immettere di nuovo le credenziali.

## <a name="urls-and-ip-address-ranges"></a>URL e intervalli di indirizzi IP
Teams richiede la connettività a Internet. Per informazioni sugli endpoint che devono essere raggiungibili per i clienti che usano Teams nei piani di Office 365, nel cloud per enti pubblici e in altri cloud, vedere [URL e intervalli di indirizzi IP per Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). 

> [!IMPORTANT]
> Attualmente Teams richiede l'accesso sulla porta TCP 443 al servizio Google ssl.gstatic.com (https://ssl.gstatic.com) per tutti gli utenti. Questo avviene anche se non si usa Gstatic. Teams rimuoverà il requisito presto (all'inizio del 2020) e questo articolo verrà aggiornato di conseguenza.

## <a name="troubleshooting-modern-authentication"></a>Risoluzione dei problemi relativi all'autenticazione moderna

L'autenticazione moderna è disponibile per tutte le organizzazioni che usano Teams, quindi se gli utenti non riescono a completare il processo potrebbe esserci un problema con il dominio o con l'account di Office 365 Enterprise dell'organizzazione. 

Per altre informazioni, vedere [Perché non riesco ad accedere a Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

