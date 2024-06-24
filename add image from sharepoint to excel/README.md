# Add image from SharePoint to Excel

you can add image from attached files of sharepoint list to excel worksheet using power automate

![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/ffbdc9a8-96e6-4773-9f61-224a6176de73)
1) get items


![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/0feab11d-301b-45b6-b1cf-1c0d9f91e6bd)
2) get attached files_Apply each3

3) get attached file contents_Apply each4_Apply each3

 - The file names are the same as the contents of a specific cell in Excel. To find the cell and insert the image.

![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/0649ae3a-4b17-4ab5-bf65-c3eb537089a5)
4) compose_Apply each4_Apply each3

 - base64(body('get_attached_file_contents'))

5) run script_Apply each4_Apply each3

 - script to add image(Please create a script in the Excel file)

function main(workbook: ExcelScript.Workbook, imageBase64: string, cellAddress: string) {

  if (!imageBase64) {

    return;
  }
    let worksheet = workbook.getWorksheet("sheet1");
    let picture = workbook.getWorksheet("sheet1").addImage(imageBase64);

    picture.setName("image");

    let titleCell = worksheet.getRange("C1:C100").find(cellAddress, { matchCase: false });

    if (titleCell) {
      let targetCell = worksheet.getCell(titleCell.getRowIndex(), 4);
      picture.setTop(targetCell.getTop());
      picture.setLeft(targetCell.getLeft());

      picture.setHeight(140);
      picture.setWidth(105);
  }
}
* Contents same as filename are in C row and images will be in D row

 - cellAddress: substring(items('Apply_each_3')?['Title'],0,indexOf(items('Apply_each_3')?['Title'],'?'))

Then, Images are added to the right of cells with the same content as the SharePoint attachment file name.
