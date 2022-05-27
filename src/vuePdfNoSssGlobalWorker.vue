<style src="./annotationLayer.css"></style>
<script>

	import componentFactory from './componentFactory.js'

	const pdfjsWrapper = require('./pdfjsWrapper.js').default;
	const PDFJS = require('pdfjs-dist/es5/build/pdf.js');
	PDFJS.GlobalWorkerOptions.workerSrc = `//cdnjs.cloudflare.com/ajax/libs/pdf.js/${PDFJS.version}/pdf.worker.js`;
	const component = componentFactory(pdfjsWrapper(PDFJS));

	export default component;
</script>
