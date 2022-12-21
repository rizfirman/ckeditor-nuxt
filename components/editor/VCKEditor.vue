<template>
  <ckeditor
    v-model="editorData"
    :editor="editor"
    :config="editorConfig"
  ></ckeditor>
</template>

<script>
import CKEditor from '@ckeditor/ckeditor5-vue2'
import ClassicEditor from '@ckeditor/ckeditor5-editor-classic/src/classiceditor'

import Bold from '@ckeditor/ckeditor5-basic-styles/src/bold'
import Italic from '@ckeditor/ckeditor5-basic-styles/src/italic.js'
import Underline from '@ckeditor/ckeditor5-basic-styles/src/underline'
import Strikethrough from '@ckeditor/ckeditor5-basic-styles/src/strikethrough'

// less Heading + Essentials plugin can't input the text
import Heading from '@ckeditor/ckeditor5-heading/src/heading'
import Essentials from '@ckeditor/ckeditor5-essentials/src/essentials'

import ImageUpload from '@ckeditor/ckeditor5-image/src/imageupload'
import ImageInsert from '@ckeditor/ckeditor5-image/src/imageinsert'
import AutoImage from '@ckeditor/ckeditor5-image/src/autoimage'
import Image from '@ckeditor/ckeditor5-image/src/image'
import ImageResizeEditing from '@ckeditor/ckeditor5-image/src/imageresize/imageresizeediting'
import ImageResizeHandles from '@ckeditor/ckeditor5-image/src/imageresize/imageresizehandles'
import Base64UploadAdapter from '@ckeditor/ckeditor5-upload/src/adapters/base64uploadadapter'
import Table from '@ckeditor/ckeditor5-table/src/table'
import TableToolbar from '@ckeditor/ckeditor5-table/src/tabletoolbar'
import Indent from '@ckeditor/ckeditor5-indent/src/indent'
import IndentBlock from '@ckeditor/ckeditor5-indent/src/indentblock'
import TableProperties from '@ckeditor/ckeditor5-table/src/tableproperties'
import TableCellProperties from '@ckeditor/ckeditor5-table/src/tablecellproperties'
import Font from '@ckeditor/ckeditor5-font/src/font'
import PasteFromOffice from '@ckeditor/ckeditor5-paste-from-office/src/pastefromoffice'
import List from '@ckeditor/ckeditor5-list/src/list'
import ListProperties from '@ckeditor/ckeditor5-list/src/listproperties'
import Alignment from '@ckeditor/ckeditor5-alignment/src/alignment'

export default {
  name: 'VCKEditor',
  components: { ckeditor: CKEditor.component },
  props: {
    value: {
      type: String,
    },
  },
  computed: {
    editorData: {
      get() {
        return this.value
      },
      set(value) {
        this.$emit('input', value)
      },
    },
  },
  data() {
    return {
      editor: ClassicEditor,
      editorConfig: {
        plugins: [
          Bold,
          Italic,
          Underline,
          Strikethrough,
          Heading,
          Essentials,
          ImageUpload,
          ImageInsert,
          AutoImage,
          Image,
          ImageResizeEditing,
          ImageResizeHandles,
          Base64UploadAdapter,
          Table,
          TableToolbar,
          Indent,
          IndentBlock,
          List,
          ListProperties,
          TableProperties,
          TableCellProperties,
          Font,
          PasteFromOffice,
          Alignment,

          function (editor) {
          
            editor.keystrokes.set('Tab', (data, cancel) => {
              // indent first line of the paragraph with tab

              const keyEvent = data.domEvent
              console.log(keyEvent)
              if (keyEvent.key === 'Tab') {
                console.log('shift')
                editor.model.change((writer) => {
                  console.log('tab')
                  const selection = editor.model.document.selection
                  const position = selection.getFirstPosition()
                  const text = writer.createText('\u00A0 \u00A0')
                  editor.model.insertContent(text, position)
                })
                cancel()
              }
            })
          }
        ],

        toolbar: {
          items: [
            'heading',
            '|',
            'alignment',
            '|',
            'bold',
            'italic',
            'strikethrough',
            'underline',
            'subscript',
            'superscript',
            '|',
            'link',
            '|',
            'bulletedList',
            'numberedList',
            'todoList',
            '-', // break point
            'fontfamily',
            'fontsize',
            'fontColor',
            'fontBackgroundColor',
            '|',
            'code',
            'codeBlock',
            '|',
            'insertTable',
            '|',
            'outdent',
            'indent',
            '|',
            'uploadImage',
            'blockQuote',
          ],
        },
        table: {
          contentToolbar: [
            'tableColumn',
            'tableRow',
            'mergeTableCells',
            'tableProperties',
            'tableCellProperties',
          ],
        },
        indentBlock: {
          offset: 1,
          unit: 'em',
        },

        language: 'en',
      },
      list: {
        properties: {
          styles: true,
          startIndex: true,
          reversed: true,
        },
      },
    }
  },
}
</script>

<style>
.custom-block-indent-a {
  margin-left: 10%;
}

.custom-block-indent-b {
  margin-left: 20%;
}

.custom-block-indent-c {
  margin-left: 30%;
}
.ck-toolbar {
  background-color: #fff;
  border-top-right-radius: 6px !important;
  border-top-left-radius: 6px !important;
}
table {
  border-collapse: collapse;
}

.ck.ck-editor {
  width: 400px;
}

.ck-content {
  height: 300px;
}
</style>
