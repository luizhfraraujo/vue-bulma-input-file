<template>
  <div class="vue-bulma">
      <div class="file">
        <label class="file-label">
            <input class="file-input" type="file" @change="onChange" name="vue-bulma">
            <span class="file-cta">
            <span class="file-icon">
                <i class="fa fa-upload"></i>
            </span>
            <span v-show="showFileLabel" class="file-label">
                {{fileLabel}}
            </span>
            </span>
        </label>
        </div>
  </div>
</template>

<script>
export default {
  props: {
    showFileLabel: {
      type: Boolean,
      default: true
    },
    fileLabel: {
      type: String,
      default: ''
    },
  },
  data() {
    return {
      file: null,
      preview: null,
      visiblePreview: false
    };
  },
  methods: {
    onChange(e) {
      const files = e.target.files || e.dataTransfer.files;

      if (!files.length) {
        return;
      }

      const file = files[0];
      const size = file.size && (file.size / Math.pow(1000, 2));
      console.log(file);
    }
  }
};
</script>