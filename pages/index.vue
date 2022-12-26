<template>
  <client-only>
    <div>
      <div style="display: flex; justify-content: center">
        <VCKEditor v-model="text" />
      </div>

      <div v-html="text"></div>
    </div>
  </client-only>
</template>

<script>
// let Bold
// let Italic
// let Underline
// let Strikethrough
// let Heading
// let Essentials
// let ImageUpload
// let ImageInsert
// let AutoImage
// let Image
// let ImageResizeEditing
// let ImageResizeHandles
// let Base64UploadAdapter
// let Table
// let TableToolbar
// let TableColumnResize
// let Indent
// let IndentBlock
// let TableProperties
// let TableCellProperties
// let Font
// let PasteFromOffice
// let List
// let ListProperties
// let Alignment
// if (process.client) {
//   Bold = require('@ckeditor/ckeditor5-basic-styles/src/bold')
//   Italic = require('@ckeditor/ckeditor5-basic-styles/src/italic.js')
//   Underline = require('@ckeditor/ckeditor5-basic-styles/src/underline')
//   Strikethrough = require('@ckeditor/ckeditor5-basic-styles/src/strikethrough')
//   // less Heading + Essentials plugin can't input the text
//   Heading = require('@ckeditor/ckeditor5-heading/src/heading')
//   Essentials = require('@ckeditor/ckeditor5-essentials/src/essentials')
//   ImageUpload = require('@ckeditor/ckeditor5-image/src/imageupload')
//   ImageInsert = require('@ckeditor/ckeditor5-image/src/imageinsert')
//   AutoImage = require('@ckeditor/ckeditor5-image/src/autoimage')
//   Image = require('@ckeditor/ckeditor5-image/src/image')
//   ImageResizeEditing = require('@ckeditor/ckeditor5-image/src/imageresize/imageresizeediting')
//   ImageResizeHandles = require('@ckeditor/ckeditor5-image/src/imageresize/imageresizehandles')
//   Base64UploadAdapter = require('@ckeditor/ckeditor5-upload/src/adapters/base64uploadadapter')
//   Table = require('@ckeditor/ckeditor5-table/src/table')
//   TableToolbar = require('@ckeditor/ckeditor5-table/src/tabletoolbar')
//   TableColumnResize = require('@ckeditor/ckeditor5-table/src/tablecolumnresize')
//   Indent = require('@ckeditor/ckeditor5-indent/src/indent')
//   IndentBlock = require('@ckeditor/ckeditor5-indent/src/indentblock')
//   TableProperties = require('@ckeditor/ckeditor5-table/src/tableproperties')
//   TableCellProperties = require('@ckeditor/ckeditor5-table/src/tablecellproperties')
//   Font = require('@ckeditor/ckeditor5-font/src/font')
//   PasteFromOffice = require('@ckeditor/ckeditor5-paste-from-office/src/pastefromoffice')
//   List = require('@ckeditor/ckeditor5-list/src/list')
//   ListProperties = require('@ckeditor/ckeditor5-list/src/listproperties')
//   Alignment = require('@ckeditor/ckeditor5-alignment/src/alignment')
// }

export default {
  data() {
    return {
      text: 'Hello World!!'
      // editorConfig: {
      //   plugins: [
      //     Bold,
      //     Italic,
      //     Underline,
      //     Strikethrough,
      //     Heading,
      //     Essentials,
      //     ImageUpload,
      //     ImageInsert,
      //     AutoImage,
      //     Image,
      //     ImageResizeEditing,
      //     ImageResizeHandles,
      //     Base64UploadAdapter,
      //     Table,
      //     TableToolbar,
      //     Indent,
      //     IndentBlock,
      //     List,
      //     ListProperties,
      //     TableProperties,
      //     TableCellProperties,
      //     Font,
      //     PasteFromOffice,
      //     Alignment,
      //     TableColumnResize,
      //     function (editor) {
          
      //       editor.keystrokes.set('Tab', (data, cancel) => {
      //         // indent first line of the paragraph with tab
      //         const keyEvent = data.domEvent
      //         console.log(keyEvent)
      //         if (keyEvent.key === 'Tab') {
      //           console.log('shift')
      //           editor.model.change((writer) => {
      //             console.log('tab')
      //             const selection = editor.model.document.selection
      //             const position = selection.getFirstPosition()
      //             const text = writer.createText('\u00A0 \u00A0')
      //             editor.model.insertContent(text, position)
      //           })
      //           cancel()
      //         }
      //       })
      //     }
      //   ],
      //   toolbar: {
      //     items: [
      //       'heading',
      //       '|',
      //       'alignment',
      //       '|',
      //       'bold',
      //       'italic',
      //       'strikethrough',
      //       'underline',
      //       'subscript',
      //       'superscript',
      //       '|',
      //       'link',
      //       '|',
      //       'bulletedList',
      //       'numberedList',
      //       'todoList',
      //       '-', // break point
      //       'fontfamily',
      //       'fontsize',
      //       'fontColor',
      //       'fontBackgroundColor',
      //       '|',
      //       'code',
      //       'codeBlock',
      //       '|',
      //       'insertTable',
      //       '|',
      //       'outdent',
      //       'indent',
      //       '|',
      //       'uploadImage',
      //       'blockQuote',
      //     ],
      //   },
      //   table: {
      //     contentToolbar: [
      //       'tableColumn',
      //       'tableRow',
      //       'mergeTableCells',
      //       'tableProperties',
      //       'tableCellProperties',
      //     ],
      //   },
      //   indentBlock: {
      //     offset: 1,
      //     unit: 'em',
      //   },
      //   language: 'en',
      // }
    }
  },
  mounted() {
    // if (process.client) {
    //   this.editorConfig = {
    //     plugins: [
    //       Bold,
    //       Italic,
    //       Underline,
    //       Strikethrough,
    //       Heading,
    //       Essentials,
    //       ImageUpload,
    //       ImageInsert,
    //       AutoImage,
    //       Image,
    //       ImageResizeEditing,
    //       ImageResizeHandles,
    //       Base64UploadAdapter,
    //       Table,
    //       TableToolbar,
    //       Indent,
    //       IndentBlock,
    //       List,
    //       ListProperties,
    //       TableProperties,
    //       TableCellProperties,
    //       Font,
    //       PasteFromOffice,
    //       Alignment,
    //       TableColumnResize,
    //       function (editor) {
          
    //         editor.keystrokes.set('Tab', (data, cancel) => {
    //           // indent first line of the paragraph with tab
    //           const keyEvent = data.domEvent
    //           console.log(keyEvent)
    //           if (keyEvent.key === 'Tab') {
    //             console.log('shift')
    //             editor.model.change((writer) => {
    //               console.log('tab')
    //               const selection = editor.model.document.selection
    //               const position = selection.getFirstPosition()
    //               const text = writer.createText('\u00A0 \u00A0')
    //               editor.model.insertContent(text, position)
    //             })
    //             cancel()
    //           }
    //         })
    //       }
    //     ],
    //     toolbar: {
    //       items: [
    //         'heading',
    //         '|',
    //         'alignment',
    //         '|',
    //         'bold',
    //         'italic',
    //         'strikethrough',
    //         'underline',
    //         'subscript',
    //         'superscript',
    //         '|',
    //         'link',
    //         '|',
    //         'bulletedList',
    //         'numberedList',
    //         'todoList',
    //         '-', // break point
    //         'fontfamily',
    //         'fontsize',
    //         'fontColor',
    //         'fontBackgroundColor',
    //         '|',
    //         'code',
    //         'codeBlock',
    //         '|',
    //         'insertTable',
    //         '|',
    //         'outdent',
    //         'indent',
    //         '|',
    //         'uploadImage',
    //         'blockQuote',
    //       ],
    //     },
    //     table: {
    //       contentToolbar: [
    //         'tableColumn',
    //         'tableRow',
    //         'mergeTableCells',
    //         'tableProperties',
    //         'tableCellProperties',
    //       ],
    //     },
    //     indentBlock: {
    //       offset: 1,
    //       unit: 'em',
    //     },
    //     language: 'en',
    //   }
    // }
  }
}
</script>
