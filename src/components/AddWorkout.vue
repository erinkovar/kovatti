<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label>Day</label>
            <input type="text" v-model="day" placeholder="Monday">
        </div>
        <div class="form-control">
            <label>Type</label>
            <select name="type" v-model="type">
                <option value="">--Please choose an option--</option>
                <option value="warmup">Warmup</option>
                <option value="core">Core</option>
                <option value="macro">Macro</option>
                <option value="structure">Structure</option>
                <option value="workout">Workout</option>
                <option value="gymnastics">Gymnastics</option>
            </select>
        </div>
        <div class="form-control">
            <label>Description</label>
            <editor
            v-model="description"
            initialValue="<p>50 Abmat situps... </p>"
            apiKey="7jfmkkt6zqswz2jo16bl2618zjgnrjdls2tvcydg1v27bxdm"
            :init="{
            height: 500,
            menubar: false,
            plugins: [
                'advlist autolink lists link image charmap',
                'searchreplace visualblocks code fullscreen',
                'print preview anchor insertdatetime media',
                'paste code help wordcount table'
            ],
            toolbar:
                'undo redo | formatselect | bold italic | \
                alignleft aligncenter alignright | \
                bullist numlist outdent indent | help'
            }"
        >
        </editor>
        </div>
        
        <input type="submit" value="Save Workout" class="btn btn-block">
        // Add additional Category
    </form>
</template>

<script>
import Editor from '@tinymce/tinymce-vue'

export default {
    name: "AddWorkout",
    data() {
        return {
            day: "",
            type: "",
            description: "",
        };
    },
    components: {
        editor: Editor,
    },
    methods: {
        onSubmit(e) {
            e.preventDefault();

            if (!this.day || !this.type || !this.description) {
                alert("Please add a workout");
                return;
            };

            const newWorkout = {
                day: this.day,
                type: this.type,
                description: this.description,
            };

            this.$emit('add-workout', newWorkout);
            this.day = '';
            this.type = '';
            this.description = '';
        }
    }
}
</script>

<style scoped>
    .form-control {
        margin: 20px 0;
    }
    .form-control label {
        display: block;
    }
    .form-control input,
    .form-control select {
        width: 100%;
        height: 40px;
        margin: 5px;
        padding: 3px 7px;
        font-size: 17px;
    }
    .form-control .tox-tinymce {

    }
</style>