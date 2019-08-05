---
title: Configurare i tipi di indirizzi IP in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Riepilogo: esaminare le considerazioni di tipo indirizzo IP seguenti prima di implementare Skype for Business Server.'
ms.openlocfilehash: 21e6254255766874872a342a2316dc8cddd5f9d2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194913"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurare i tipi di indirizzi IP in Skype for Business

**Riepilogo:** Esaminare le considerazioni di tipo indirizzo IP seguenti prima di implementare Skype for Business Server.

I tipi di indirizzo IP vengono distribuiti usando le impostazioni della topologia configurate in Generatore di topologie. Questa sezione descrive come distribuire i tipi di indirizzo IP in server front-end, Mediation Server e Edge Server.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Distribuire i tipi di indirizzi IP in un Front End Server

Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un server front-end.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Per distribuire i tipi di indirizzo IP in un server front-end

1. In **pool Enterprise Edition front-end**fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**. In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .

2. Nella finestra di dialogo **modifica proprietà** selezionare il tipo di indirizzo IP che si vuole configurare. Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**.

   **Finestra di dialogo Modifica proprietà per il pool del server front-end**

   - **Usare tutti gli indirizzi IP**configurati. Selezionare questa opzione se si vuole consentire l'uso di qualsiasi indirizzo IP definito nel computer.

     > [!NOTE]
     > Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).

   - **Limitare l'utilizzo del servizio agli indirizzi IP selezionati**. Selezionare questa opzione per specificare un indirizzo specifico da usare nel nuovo server. Se si seleziona questa opzione, è necessario immettere un valore per l' **indirizzo IP principale**.

   - **Indirizzo IP principale**. Immettere un indirizzo IP che il server userà per tutte le comunicazioni eccetto PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo di selezione.

   - **Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel server front-end. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.

> [!NOTE]
> L'installazione di schede di interfaccia di rete aggiuntive (NIC) per supportare la configurazione degli indirizzi IP PSTN (o per qualsiasi altro motivo) nei server front-end non è supportata. Per altre informazioni sulle configurazioni di NIC supportate per Skype for Business Server, vedere [piattaforme hardware server per Lync server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Distribuire i tipi di indirizzi IP in un Mediation Server

Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un Mediation Server.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Per distribuire i tipi di indirizzo IP in un Mediation Server

- In Generatore di topologia, in **pool**di mediazione, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**. In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .

- Nella finestra di dialogo **modifica proprietà** selezionare il tipo di indirizzo IP che si vuole configurare. Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.

   **Finestra di dialogo Modifica proprietà per il pool di Mediation Server**

  - **Usare tutti gli indirizzi IP**configurati. Selezionare questa opzione se si vuole consentire l'uso di qualsiasi indirizzo IP definito nel computer.

    > [!NOTE]
    > Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).

  - **Limitare l'utilizzo del servizio agli indirizzi IP selezionati**. Selezionare questa opzione per specificare un indirizzo specifico da usare nel nuovo server. Se si seleziona questa opzione, è necessario immettere un valore per l'indirizzo IP principale.

  - **Indirizzo IP principale**. Immettere un indirizzo IP che il server userà per tutte le comunicazioni eccetto PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo di selezione.

  - **Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel server front-end. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.
> [!IMPORTANT]
> Supportiamo solo due schede di rete su server di mediazione *dedicati* . Se il ruolo di mediazione sServer è collocato sul front-end, le schede di rete doppie non sono supportate. 

> [!NOTE]
> - Per altre informazioni sulle configurazioni di NIC supportate per Skype for Business Server 2015, vedere [hardware per Skype for Business server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Per altre informazioni sulle configurazioni di NIC supportate per Skype for Business Server 2019, vedere [hardware per Skype for Business server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Distribuire i tipi di indirizzi IP in un server perimetrale

Con generatore di topologie eseguire la procedura seguente:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Per distribuire i tipi di indirizzo IP in un server perimetrale

1. In Generatore di topologie, in **pool di bordi**, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**. In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .

2. Nella finestra **modifica proprietà** selezionare la configurazione dell'indirizzo IP che si vuole supportare.

3. Per ogni tipo di indirizzo selezionato, è necessario specificare indirizzi interni ed esterni appropriati.
