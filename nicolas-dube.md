# Revue de code de Nicolas Dubé

## Le Code

**Le camelCase n'est pas respecté**

popover au lien de popOver
```ts
var popover = new Popover(document.getElementById('errorPopover'), {
    title: 'Error',
    content: 'An error occurred while playing audio file.',
    trigger: 'manual'
});
popover.show();
```


**Bouton stop**

On ne peut pas faire stop quand la musique est en pause



## Autres

**Esthéthique**

[Les boutons pourraient être plus stylisé](https://getbootstrap.com/docs/4.1/components/buttons/)


**Aucun emit utilisé**

Le code utilise des stores, qui est une vielle fonctionnalité


**Valeurs non utilisés**

La valeur oldValue n'est pas utilisé
```ts
watch(audio, (newValue, oldValue) => {
    formattedDuration.value = formatAudioDuration(newValue.duration)

    newValue.addEventListener('ended', () => {
        store.commit('nextSong');
    });
})
```


**SetInterval**

SetInterval n'est pas le plus performant.
Il est préférable d'utiliser [TimeRange](https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges)