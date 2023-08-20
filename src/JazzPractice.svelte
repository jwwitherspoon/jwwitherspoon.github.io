<script>
    const keys = ['A','A#','Bb','B','C','C#','Db','D','D#','Eb','E','F','F#','Gb','G','G#'];
    const tonalities = [
        ['', 'maj', 'ma', 'M'], // Major
        ['∆', 'm', 'mi', 'min', '-'], // Minor
        ['°', 'dim'], // Fully diminished
        ['+', 'aug', '(#5)'], // Augmented
        ['Ø'], // Half Diminished
    ];
    const extensions = ['','6','7','9','11','13'];

    let message = 'Click a button to generate practice material!';

    function getRandomIndex(arr) {
        return Math.floor(Math.random() * arr.length);
    }

    function generateKey() {
        const key = keys[getRandomIndex(keys)];
        message = key;
    }

    function generateChord() {
        const root = keys[getRandomIndex(keys)];
        const tonalityType = tonalities[getRandomIndex(tonalities)];
        const tonality = tonalityType[getRandomIndex(tonalityType)];
        const extension = extensions[getRandomIndex(extensions)];
        message = root + tonality + extension;
    }
</script>

<div class="row justify-content-center">
    <h2>Jazz Practice Tools</h2>
</div>
<div>
    <p class="my-4">{message}</p>
</div>
<div class="row justify-content-around">
    <div class="col align-items-center">
        <button type="button" class="btn btn-primary" on:click={generateKey}>Random Key</button>
    </div>
    <div class="col align-items-center">
        <button type="button" class="btn btn-primary" on:click={generateChord}>Random Chord</button>
    </div>
</div>

<style scoped>
    h2 {
        padding: 0 1rem;
    }

    .btn {
        margin: 10px;
    }
</style>
