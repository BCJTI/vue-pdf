<style src="./annotationLayer.css"></style>
<script>

	import componentFactory from './componentFactory.js'

	if ( process.env.VUE_ENV !== 'server' ) {
		var pdfjsWrapper = require('./pdfjsWrapper.js').default;
		// var PDFJS = require('pdfjs-dist/es5/build/pdf.js');
		var PDFJS = require('pdfjs-dist/es5/build/pdf.js');
		PDFJS.GlobalWorkerOptions.workerSrc = `//cdnjs.cloudflare.com/ajax/libs/pdf.js/${pdfjs.version}/pdf.worker.js`;
		var component = componentFactory(pdfjsWrapper(PDFJS));
	} else {
		var component = componentFactory({});
	}

	export default component;
</script>
